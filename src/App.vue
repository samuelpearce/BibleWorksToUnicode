<!--
We can create two-way bindings between state and form inputs using the v-model directive.
-->
<style>
@import 'https://cdn.jsdelivr.net/gh/yegor256/tacit@gh-pages/tacit-css.min.css';

.letter {
  font-family: "bwgrkn";
}

</style>

<script setup>
import {ref, watchEffect} from 'vue'

let data = ref([]) // (await fetch(url)).json()
const showModal = ref(false)

const text = ref('text23')
const selected = ref('bwgrkn')
const converted = ref('')

watchEffect(() => convert(text.value))


const API_URL = `/data/bwgrkn.json`

watchEffect(async () => {
  // this effect will run immediately and then
  // re-run whenever currentBranch.value changes
  const url = `${API_URL}`
  data.value = await (await fetch(url)).json()
})
function convert(textlocal) {
  
  let a = data.value

	converted.value = textlocal
  for ( const [key,value] of Object.entries( a ) ) {
		converted.value = converted.value.replaceAll(key, value)
  }
}

function copy(e) {
    navigator.clipboard.writeText(converted.value)  
}
</script>

<template>
  <h1>
    BibleWorks Greek to Unicode
  </h1>
  <p>Quickly convert BibleWorks Greek text to Unicode.</p>

  <h2>Step 1: Select Font</h2>
  <select v-model="selected" style="width: 50%">
    <option value="bwgrkn" selected>Greek Normal (bwgrkn)</option>
    <option value="bwgrkl">Greek Light (bwgrkl)</option>
    <option value="bwgrki">Greek Italics (bwgrki)</option>
    <option disabled value="bwgrkd">Greek Diacritics (bwgrkd) (to be implemeted)</option>    
  </select>
  <br/>
  <h2>
    Step 2: Enter Bible Works text
  </h2>
  <input type="text" v-model="text" style="width: 50%" />
  <br/>

  <h3>
    Step 3: Compare both lines
  </h3>

  <div class="original">
    <span class="letter">{{ text }}</span>
    - Your text in BibleWorks Greek
  </div>
  <div class="original">
    <span>{{ converted }}</span>
    - Your text in Unicode
  </div>


  <h2>
    Your Unicode text
  </h2>
  
  <input v-on:focus="$event.target.select()" 
           ref="convertedTextBox" 
           readonly 
           type="text" 
           v-model="converted" 
           style="width: 50%" />
	
  <button id="show-modal" @click="copy">Copy to clipboard</button>

 
  
</template>


