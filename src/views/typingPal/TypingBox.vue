<template>
  <div class="input-container">
    <textarea
      v-model="inputText"
      placeholder="Type Hello..."
      class="text-input"
      @input="updateSuggestions"
    ></textarea>
    <div v-if="suggestions.length" class="suggestions-container">
      <div
        v-for="(suggestion, index) in suggestions"
        :key="index"
        class="suggestion"
        @click="completeSentence(suggestion)"
      >
        {{ suggestion }}
      </div>
    </div>
  </div>
</template>

<script>
import { suggestion } from '@tiptap/suggestion';

export default {
  data() {
    return {
      inputText: '',
      suggestions: [],
    };
  },
  methods: {
    updateSuggestions() {
      const words = this.inputText.split(' ');
      const lastWord = words[words.length - 1].toLowerCase();

      // Smarter suggestion logic
      if (lastWord === 'hello') {
        this.suggestions = ['Hello, how are you?', 'Hello, good morning!'];
      } else if (lastWord === 'vue') {
        this.suggestions = ['Vue.js is a progressive framework.', 'Vue is great for building user interfaces.'];
      } else if (lastWord === 'ai') {
        this.suggestions = ['AI is transforming technology.', 'AI helps in predictive analytics.'];
      } else {
        this.suggestions = [];
      }
    },
    completeSentence(suggestion) {
      const words = this.inputText.split(' ');
      words.pop(); // Remove the last word
      this.inputText = words.join(' ') + ' ' + suggestion; // Append the suggestion
      this.suggestions = [];
    },
  },
};
 
</script>

<style scoped>
.input-container {
  perspective: 1000px;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: center;
  height: 100vh;
}

.text-input {
  margin-top: 20px;
  width: 80vw;
  height: 60vh;
  padding: 10px;
  border: none;
  border-radius: 8px;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2), 0 2px 5px rgba(0, 0, 0, 0.2);
  font-size: 30px;
  line-height: 1.2;
  text-align: left;
  display: block;
  overflow-y: auto;
  box-sizing: border-box;
  transition: transform 0.2s;
  resize: none;
}

.text-input:focus {
  outline: none;
  transform: translateY(-2px);
  box-shadow: 0 6px 15px rgba(0, 0, 0, 0.3), 0 3px 7px rgba(0, 0, 0, 0.3);
}

.suggestions-container {
  margin-top: 10px;
  width: 80vw;
  background-color: #f9f9f9;
  border-radius: 8px;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
  max-height: 150px;
  overflow-y: auto;
}

.suggestion {
  padding: 10px;
  cursor: pointer;
  border-bottom: 1px solid #eee;
}

.suggestion:hover {
  background-color: #e0e0e0;
}
</style>
