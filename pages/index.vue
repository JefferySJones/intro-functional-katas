<script setup>
import isEqual from 'lodash/isEqual'
import { Buffer } from 'buffer'

/**
 *    $$\   $$\           $$\                     $$$$$$\ 
 *    $$ | $$  |          $$ |                    \_$$  _|
 *    $$ |$$  / $$$$$$\ $$$$$$\    $$$$$$\          $$ |  
 *    $$$$$  /  \____$$\\_$$  _|   \____$$\         $$ |  
 *    $$  $$<   $$$$$$$ | $$ |     $$$$$$$ |        $$ |  
 *    $$ |\$$\ $$  __$$ | $$ |$$\ $$  __$$ |        $$ |  
 *    $$ | \$$\\$$$$$$$ | \$$$$  |\$$$$$$$ |      $$$$$$\ 
 *    \__|  \__|\_______|  \____/  \_______|      \______|                                          
 * KATA 1
 * 
 * Implement a function that takes an array of integers 
 * and returns the sum of all the even numbers. Use filter 
 * to get the even numbers, and then reduce to sum them up.
 */

const mixedNumbers = [1, 5, 7, 2, 3, 40, 10, 2, 99, 4239, 4009, 320, 322, 321, 4058, 9, 1337]

const summedEvens = ref(sumEvens(mixedNumbers))
const summedEvensExpected = ref(4754)
const summedEvensCorrect = reactive(summedEvens.value == summedEvensExpected.value)

function sumEvens (mixedNumbers = [1, 2, 3]) {
    return mixedNumbers.filter((number) => number % 2 == 0).reduce((a, c, i) => a + c)
}

/**
 *    $$\   $$\           $$\                     $$$$$$\ $$$$$$\ 
 *    $$ | $$  |          $$ |                    \_$$  _|\_$$  _|
 *    $$ |$$  / $$$$$$\ $$$$$$\    $$$$$$\          $$ |    $$ |  
 *    $$$$$  /  \____$$\\_$$  _|   \____$$\         $$ |    $$ |  
 *    $$  $$<   $$$$$$$ | $$ |     $$$$$$$ |        $$ |    $$ |  
 *    $$ |\$$\ $$  __$$ | $$ |$$\ $$  __$$ |        $$ |    $$ |  
 *    $$ | \$$\\$$$$$$$ | \$$$$  |\$$$$$$$ |      $$$$$$\ $$$$$$\ 
 *    \__|  \__|\_______|  \____/  \_______|      \______|\______|                                       
 * KATA 2
 * 
 * Implement a function that takes an array of strings 
 * and returns a new array with all the strings converted 
 * to uppercase. Use map to transform each string.
 */

const normalStrings = ["ok", "i'll do that", "no problem", "i am not angry with you"]

const angryStrings = ref(makeStringsAngry(normalStrings))
const angryStringsExpected = ref(["OK", "I'LL DO THAT", "NO PROBLEM", "I AM NOT ANGRY WITH YOU"])
const angryStringsCorrect = reactive(isEqual(angryStrings.value, angryStringsExpected.value))

function makeStringsAngry (normalStrings = ['string']) {
    return normalStrings.map(string => string.toUpperCase())
}

/**
 *    $$\   $$\           $$\                     $$$$$$\ $$$$$$\ $$$$$$\ 
 *    $$ | $$  |          $$ |                    \_$$  _|\_$$  _|\_$$  _|
 *    $$ |$$  / $$$$$$\ $$$$$$\    $$$$$$\          $$ |    $$ |    $$ |  
 *    $$$$$  /  \____$$\\_$$  _|   \____$$\         $$ |    $$ |    $$ |  
 *    $$  $$<   $$$$$$$ | $$ |     $$$$$$$ |        $$ |    $$ |    $$ |  
 *    $$ |\$$\ $$  __$$ | $$ |$$\ $$  __$$ |        $$ |    $$ |    $$ |  
 *    $$ | \$$\\$$$$$$$ | \$$$$  |\$$$$$$$ |      $$$$$$\ $$$$$$\ $$$$$$\ 
 *    \__|  \__|\_______|  \____/  \_______|      \______|\______|\______|
 * KATA 3
 * 
 * Implement a function that takes an array of objects and returns 
 * a new array with just the name property of each object. 
 * Use map to transform each object.
 */

const numbersToMultiply = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

const multipliedNumbers = ref(multiplyByTwo(numbersToMultiply))
const multipliedNumbersExpected = ref([2, 4, 6, 8, 10, 12, 14, 16, 18, 20])
const multipliedNumbersCorrect = reactive(isEqual(multipliedNumbers.value, multipliedNumbersExpected.value))

function multiplyByTwo(numbersToMultiply = [2]) {
    return numbersToMultiply.map(number => number * 2)
}


/**
 *    $$\   $$\           $$\                     $$$$$$\ $$\    $$\ 
 *    $$ | $$  |          $$ |                    \_$$  _|$$ |   $$ |
 *    $$ |$$  / $$$$$$\ $$$$$$\    $$$$$$\          $$ |  $$ |   $$ |
 *    $$$$$  /  \____$$\\_$$  _|   \____$$\         $$ |  \$$\  $$  |
 *    $$  $$<   $$$$$$$ | $$ |     $$$$$$$ |        $$ |   \$$\$$  / 
 *    $$ |\$$\ $$  __$$ | $$ |$$\ $$  __$$ |        $$ |    \$$$  /  
 *    $$ | \$$\\$$$$$$$ | \$$$$  |\$$$$$$$ |      $$$$$$\    \$  /   
 *    \__|  \__|\_______|  \____/  \_______|      \______|    \_/    
 * KATA 4
 * 
 * Implement a function that takes an array of objects and returns 
 * a new array with just the name and quote property of each object.
 * Use map to transform each object.
 */

const chars = 'JTVCJTdCJTIybmFtZSUyMiUzQSUyMk1pY2hhZWwlMjBTY290dCUyMiUyQyUyMmpvYlRpdGxlJTIyJTNBJTIyUmVnaW9uYWwlMjBNYW5hZ2VyJTIyJTJDJTIycGVyc29uYWxpdHlUeXBlJTIyJTNBJTIyRXh0cm92ZXJ0ZWQlMkMlMjBhdHRlbnRpb24tc2Vla2luZyUyQyUyMGluc2VjdXJlJTIyJTJDJTIycXVvdGUlMjIlM0ElMjJUaGF0JUUyJTgwJTk5cyUyMHdoYXQlMjBzaGUlMjBzYWlkISUyMiU3RCUyQyU3QiUyMm5hbWUlMjIlM0ElMjJEd2lnaHQlMjBTY2hydXRlJTIyJTJDJTIyam9iVGl0bGUlMjIlM0ElMjJBc3Npc3RhbnQlMjB0byUyMHRoZSUyMFJlZ2lvbmFsJTIwTWFuYWdlciUyMiUyQyUyMnBlcnNvbmFsaXR5VHlwZSUyMiUzQSUyMkhhcmR3b3JraW5nJTJDJTIwbG95YWwlMkMlMjBzb2NpYWxseSUyMGF3a3dhcmQlMjIlMkMlMjJxdW90ZSUyMiUzQSUyMkJlYXJzLiUyMEJlZXRzLiUyMEJhdHRsZXN0YXIlMjBHYWxhY3RpY2EuJTIyJTdEJTJDJTdCJTIybmFtZSUyMiUzQSUyMkppbSUyMEhhbHBlcnQlMjIlMkMlMjJqb2JUaXRsZSUyMiUzQSUyMlNhbGVzJTIwUmVwcmVzZW50YXRpdmUlMjIlMkMlMjJwZXJzb25hbGl0eVR5cGUlMjIlM0ElMjJXaXR0eSUyQyUyMGNoYXJtaW5nJTJDJTIwcHJhY3RpY2FsJTIwam9rZXIlMjIlMkMlMjJxdW90ZSUyMiUzQSUyMkJlYXJzJTJDJTIwYmVldHMlMkMlMjBCYXR0bGVzdGFyJTIwR2FsYWN0aWNhISUyMiU3RCUyQyU3QiUyMm5hbWUlMjIlM0ElMjJQYW0lMjBCZWVzbHklMjIlMkMlMjJqb2JUaXRsZSUyMiUzQSUyMlJlY2VwdGlvbmlzdCUyMiUyQyUyMnBlcnNvbmFsaXR5VHlwZSUyMiUzQSUyMlN3ZWV0JTJDJTIwc2h5JTJDJTIwY3JlYXRpdmUlMjIlMkMlMjJxdW90ZSUyMiUzQSUyMkklMjBkb24lRTIlODAlOTl0JTIwaGF0ZSUyMGl0LiUyMEklMjBqdXN0JTIwZG9uJUUyJTgwJTk5dCUyMGxpa2UlMjBpdCUyMGF0JTIwYWxsJTIwYW5kJTIwaXQlRTIlODAlOTlzJTIwdGVycmlibGUuJTIyJTdEJTJDJTdCJTIybmFtZSUyMiUzQSUyMlJ5YW4lMjBIb3dhcmQlMjIlMkMlMjJqb2JUaXRsZSUyMiUzQSUyMlRlbXAlMkMlMjBsYXRlciUyMFZQJTIwb2YlMjBOb3J0aGVhc3QlMjBTYWxlcyUyMiUyQyUyMnBlcnNvbmFsaXR5VHlwZSUyMiUzQSUyMkFycm9nYW50JTJDJTIwYW1iaXRpb3VzJTJDJTIwZW50aXRsZWQlMjIlMkMlMjJxdW90ZSUyMiUzQSUyMkklRTIlODAlOTltJTIwbm90JTIwYSUyMHRlbXAlMjBhbnltb3JlLiUyMEklRTIlODAlOTltJTIweW91ciUyMGJvc3MlRTIlODAlOTlzJTIwYm9zcyVFMiU4MCU5OXMlMjBib3NzJUUyJTgwJTk5cyUyMGJvc3MuJTIyJTdEJTVE'
const charSummary = 'JTVCJTdCJTIybmFtZSUyMiUzQSUyMk1pY2hhZWwlMjBTY290dCUyMiUyQyUyMnF1b3RlJTIyJTNBJTIyVGhhdCVFMiU4MCU5OXMlMjB3aGF0JTIwc2hlJTIwc2FpZCElMjIlN0QlMkMlN0IlMjJuYW1lJTIyJTNBJTIyRHdpZ2h0JTIwU2NocnV0ZSUyMiUyQyUyMnF1b3RlJTIyJTNBJTIyQmVhcnMuJTIwQmVldHMuJTIwQmF0dGxlc3RhciUyMEdhbGFjdGljYS4lMjIlN0QlMkMlN0IlMjJuYW1lJTIyJTNBJTIySmltJTIwSGFscGVydCUyMiUyQyUyMnF1b3RlJTIyJTNBJTIyQmVhcnMlMkMlMjBiZWV0cyUyQyUyMEJhdHRsZXN0YXIlMjBHYWxhY3RpY2EhJTIyJTdEJTJDJTdCJTIybmFtZSUyMiUzQSUyMlBhbSUyMEJlZXNseSUyMiUyQyUyMnF1b3RlJTIyJTNBJTIySSUyMGRvbiVFMiU4MCU5OXQlMjBoYXRlJTIwaXQuJTIwSSUyMGp1c3QlMjBkb24lRTIlODAlOTl0JTIwbGlrZSUyMGl0JTIwYXQlMjBhbGwlMjBhbmQlMjBpdCVFMiU4MCU5OXMlMjB0ZXJyaWJsZS4lMjIlN0QlMkMlN0IlMjJuYW1lJTIyJTNBJTIyUnlhbiUyMEhvd2FyZCUyMiUyQyUyMnF1b3RlJTIyJTNBJTIySSVFMiU4MCU5OW0lMjBub3QlMjBhJTIwdGVtcCUyMGFueW1vcmUuJTIwSSVFMiU4MCU5OW0lMjB5b3VyJTIwYm9zcyVFMiU4MCU5OXMlMjBib3NzJUUyJTgwJTk5cyUyMGJvc3MlRTIlODAlOTlzJTIwYm9zcy4lMjIlN0QlNUQ='
const characters = JSON.parse(decodeURIComponent(Buffer.from(chars, 'base64')))
const charactersSummary = JSON.parse(decodeURIComponent(Buffer.from(charSummary, 'base64')))

const changedCharacters = ref(characterQuotes(characters))
const changedCharactersExpected = ref(charactersSummary)
const changedCharactersCorrect = reactive(isEqual(changedCharacters.value, changedCharactersExpected.value))

function characterQuotes(characters = [{name: "bob", quote: "no", chicken: true}]) {
    return characters.map(character => ({ name: character.name, quote: character.quote }))
}


/**
 *    $$\   $$\           $$\                     $$\    $$\ 
 *    $$ | $$  |          $$ |                    $$ |   $$ |
 *    $$ |$$  / $$$$$$\ $$$$$$\    $$$$$$\        $$ |   $$ |
 *    $$$$$  /  \____$$\\_$$  _|   \____$$\       \$$\  $$  |
 *    $$  $$<   $$$$$$$ | $$ |     $$$$$$$ |       \$$\$$  / 
 *    $$ |\$$\ $$  __$$ | $$ |$$\ $$  __$$ |        \$$$  /  
 *    $$ | \$$\\$$$$$$$ | \$$$$  |\$$$$$$$ |         \$  /   
 *    \__|  \__|\_______|  \____/  \_______|          \_/    
 * KATA 5
 *                                     
 * Implement a function that takes an array of strings and 
 * returns a new array with only the strings that have 
 * a length greater than 6. Use filter to create the new array.
 */

const words = ["apple", "pear", "banana", "orange", "grapefruit", "watermelon", "pineapple", "blueberry", "raspberry"]

const filteredWords = ref(filterWords(words))
const filteredWordsExpected = ref(["grapefruit", "watermelon", "pineapple", "blueberry", "raspberry"])
const filteredWordsCorrect = reactive(JSON.stringify(filteredWords.value) === JSON.stringify(filteredWordsExpected.value))

function filterWords (words = ['longword', 'word']) {
    return words.filter(word => word.length > 6)
}


/**
 *    $$\   $$\           $$\                     $$\    $$\ $$$$$$\ 
 *    $$ | $$  |          $$ |                    $$ |   $$ |\_$$  _|
 *    $$ |$$  / $$$$$$\ $$$$$$\    $$$$$$\        $$ |   $$ |  $$ |  
 *    $$$$$  /  \____$$\\_$$  _|   \____$$\       \$$\  $$  |  $$ |  
 *    $$  $$<   $$$$$$$ | $$ |     $$$$$$$ |       \$$\$$  /   $$ |  
 *    $$ |\$$\ $$  __$$ | $$ |$$\ $$  __$$ |        \$$$  /    $$ |  
 *    $$ | \$$\\$$$$$$$ | \$$$$  |\$$$$$$$ |         \$  /   $$$$$$\ 
 *    \__|  \__|\_______|  \____/  \_______|          \_/    \______|
 * KATA 6
 *    
 * Implement a function that takes an array of objects and returns 
 * a new array with just the objects that have a property called 
 * "completed" set to true. Create a new property on each object
 * called "ezpz" that is a Boolean. Mark "ezpz" true if the task
 * contains 2 or less words.
 */

const todoItems = [
    { task: 'Write some code', completed: true },
    { task: 'Take over the world', completed: false },
    { task: 'Go for a walk', completed: true },
    { task: 'Buy groceries', completed: false },
    { task: 'Call mom', completed: true },
    { task: 'Clean the house', completed: false }
]

const completedItems = ref(filterCompleted(todoItems))
const completedItemsExpected = ref([
    { task: 'Write some code', completed: true, ezpz: false },
    { task: 'Go for a walk', completed: true, ezpz: false },
    { task: 'Call mom', completed: true, ezpz: true }
])
const completedItemsCorrect = reactive(JSON.stringify(completedItems.value) === JSON.stringify(completedItemsExpected.value))

function filterCompleted (todoItems = []) {
    return todoItems.filter(item => item.completed).map(item => ({...item, "ezpz": item.task.split(' ').length <= 2}))
}

/**
 *    $$\   $$\           $$\                     $$\    $$\ $$$$$$\ $$$$$$\ 
 *    $$ | $$  |          $$ |                    $$ |   $$ |\_$$  _|\_$$  _|
 *    $$ |$$  / $$$$$$\ $$$$$$\    $$$$$$\        $$ |   $$ |  $$ |    $$ |  
 *    $$$$$  /  \____$$\\_$$  _|   \____$$\       \$$\  $$  |  $$ |    $$ |  
 *    $$  $$<   $$$$$$$ | $$ |     $$$$$$$ |       \$$\$$  /   $$ |    $$ |  
 *    $$ |\$$\ $$  __$$ | $$ |$$\ $$  __$$ |        \$$$  /    $$ |    $$ |  
 *    $$ | \$$\\$$$$$$$ | \$$$$  |\$$$$$$$ |         \$  /   $$$$$$\ $$$$$$\ 
 *    \__|  \__|\_______|  \____/  \_______|          \_/    \______|\______|
 * KATA 7
 *    
 *   Implement a function that takes an array of numbers and returns a new array 
 *   with the square of each number. Filter out all the even numbers. Then add
 *   all of the numbers together.
 */

const totallyOriginalNumbers = [1, 5, 7, 2, 3, 10, 99, 4239, 4009, 320, 322, 321, 4058, 9, 1337]
const squaredNumbers = ref(squareAllFilterEvensAndAddAll(totallyOriginalNumbers))
const squaredNumbersExpected = ref(10034)
const squaredNumbersCorrect = reactive(JSON.stringify(squaredNumbers.value) == JSON.stringify(squaredNumbersExpected.value))

function squareAllFilterEvensAndAddAll (totallyOriginalNumbers = []) {
    return totallyOriginalNumbers.map(number => number ^ 2).filter(number => number % 2 !== 0).reduce((a,c) => a + c)
}

/**
 *    $$\   $$\           $$\                     $$\    $$\ $$$$$$\ $$$$$$\ $$$$$$\ 
 *    $$ | $$  |          $$ |                    $$ |   $$ |\_$$  _|\_$$  _|\_$$  _|
 *    $$ |$$  / $$$$$$\ $$$$$$\    $$$$$$\        $$ |   $$ |  $$ |    $$ |    $$ |  
 *    $$$$$  /  \____$$\\_$$  _|   \____$$\       \$$\  $$  |  $$ |    $$ |    $$ |  
 *    $$  $$<   $$$$$$$ | $$ |     $$$$$$$ |       \$$\$$  /   $$ |    $$ |    $$ |  
 *    $$ |\$$\ $$  __$$ | $$ |$$\ $$  __$$ |        \$$$  /    $$ |    $$ |    $$ |  
 *    $$ | \$$\\$$$$$$$ | \$$$$  |\$$$$$$$ |         \$  /   $$$$$$\ $$$$$$\ $$$$$$\ 
 *    \__|  \__|\_______|  \____/  \_______|          \_/    \______|\______|\______|
 * KATA 8
 *    
 * Implement a function that takes an array of strings and returns the longest string.
 */

const longWords = ['pneumonoultramicroscopicsilicovolcanoconiosis', 'floccinaucinihilipilification', 'antidisestablishmentarianism', 'supercalifragilisticexpialidocious', 'hippopotomonstrosesquipedaliophobia', 'chromatopsia', 'incomprehensibilities', 'otorhinolaryngological', 'psychoneuroendocrinological', 'gastroenteroanastomosis']

const longestWord = ref(getLongestWord(longWords))
const longestWordExpected = ref('pneumonoultramicroscopicsilicovolcanoconiosis')
const longestWordCorrect = reactive(longestWord.value === longestWordExpected.value)

function getLongestWord(words) {
  return words.reduce((a,c) => {
    if(c.length > a.length) {
        return c
    }
    return a
} ,'')
}

</script>

<template>
    <h1 class="text-xl px-4 pb-4 font-bold">
        Vue/Nuxt 3 Functional Programming Kata
    </h1>

    <div class="p-10">
        <p class="mb-4">
            Pure functions: A pure function is a function that always returns the same output for the same input and doesn't modify any external state. Pure functions are easy to test and reason about, and they can be composed to build more complex behavior.
            <br />
            - A pure function is like a vending machine. You put in the same inputs (money and selection) and you always get the same output (snack). The vending machine doesn't change anything outside itself (like your wallet), and you don't have to worry about the vending machine stealing your money or giving you the wrong snack.
        </p>
        <p class="mb-4">
            
        </p>
        <p class="mb-4">
            Immutability: In functional programming, data is often treated as immutable, which means that once a value is created, it cannot be changed. Instead, new values are created by applying functions to existing values. This makes it easier to reason about the behavior of a program and avoid unexpected side effects.
            <br />
            - Immutability is like a museum exhibit. Once a piece of art is placed in the exhibit, it can't be changed. Visitors can observe the art and appreciate its beauty, but they can't add to it or alter it in any way. Similarly, in functional programming, data is treated as a valuable artifact that should be preserved and protected from accidental changes.
        </p>

        <p class="mb-4">
            The following Katas will help you to practice some of the basics of functional programming. It's good to keep "pure functions" and "immutability" in mind through these examples.
        </p>
    </div>
    
    <!-- kata 1 -->
    <div class="mx-8 mb-4 p-4 bg-neutral-950 rounded-lg border-4 border-double border-indigo-400" :class="{'border-rose-400': !summedEvensCorrect}">
        <p class="text-gray-300">
            <span class="font-bold text-indigo-300">Kata I:</span>
            Implement a function called <span class="text-lime-300">sumEvens()</span> 
            that takes in <span class="text-orange-300">mixedNumbers</span> 
            and returns the sum of all the even numbers it contains.
            <br/>
            Use <span class="text-lime-300">filter()</span> to get the even numbers 
            and then <span class="text-lime-300">reduce()</span> to sum them up.
        </p>
        <div class="pt-3">
            <span class="text-lime-300">
                summedEvens(
                    <span class="text-orange-300">mixedNumbers</span>
                )
            </span>
            <span class="pl-3 text-gray-500">
                // {{ summedEvensExpected }}
            </span>
            <div>
                <span v-if="summedEvensCorrect" class="text-lime-500 font-bold text-xl">
                    ✓
                </span>
                <span v-else class="text-rose-500 font-bold text-xl">
                    ✗
                </span>
                <span :class="{'underline decoration-dotted decoration-2 decoration-rose-500': !summedEvensCorrect}">
                    {{ summedEvens }}
                </span>
            </div>
            
        </div>
    </div>

    <!-- kata 2 -->
    <div class="mx-8 mb-4 p-4 bg-neutral-950 rounded-lg border-4 border-double border-indigo-400" :class="{'border-rose-400': !angryStringsCorrect}">
        <p class="text-gray-300">
            <span class="font-bold text-indigo-300">Kata II:</span>
            Implement a function called <span class="text-lime-300">makeStringsAngry()</span> 
            that takes in <span class="text-orange-300">normalStrings</span> and returns a new array with all the strings converted to uppercase.
            <br/>
            Use <span class="text-lime-300">map()</span> to transform each string.
        </p>
        <div class="pt-3">
            <span class="text-lime-300">
                angryStrings(
                    <span class="text-orange-300">normalStrings</span>
                )
            </span>
            <span class="pl-3 text-gray-500">
                // {{ angryStringsExpected }}
            </span>
            <div>
                <span v-if="angryStringsCorrect" class="text-lime-500 font-bold text-xl">
                    ✓
                </span>
                <span v-else class="text-rose-500 font-bold text-xl">
                    ✗
                </span>
                <span :class="{'underline decoration-dotted decoration-2 decoration-rose-500': !angryStringsCorrect}">
                    {{ angryStrings }}
                </span>
            </div>
            
        </div>

        
    </div>

    <!-- kata 3 -->
    <div class="mx-8 mb-4 p-4 bg-neutral-950 rounded-lg border-4 border-double border-indigo-400" :class="{'border-rose-400': !multipliedNumbersCorrect}">
        <p class="text-gray-300">
            <span class="font-bold text-indigo-300">Kata III:</span>
            Implement a function called <span class="text-lime-300">multiplyByTwo()</span> 
            that takes in <span class="text-orange-300">numbersToMultiply</span> and returns a new array with each number multiplied by 2.
            <br/>
            Use <span class="text-lime-300">map()</span> to transform each number.

            <!-- Implement a function that takes an array of numbers and returns a new array with each number multiplied by 2. -->
        </p>
        <div class="pt-3">
            <span class="text-lime-300">
                multiplyByTwo(
                    <span class="text-orange-300">numbersToMultiply</span>
                )
            </span>
            <span class="pl-3 text-gray-500">
                // {{ multipliedNumbersExpected }}
            </span>
            <div>
                <span v-if="multipliedNumbersCorrect" class="text-lime-500 font-bold text-xl">
                    ✓
                </span>
                <span v-else class="text-rose-500 font-bold text-xl">
                    ✗
                </span>
                <span :class="{'underline decoration-dotted decoration-2 decoration-rose-500': !multipliedNumbersCorrect}">
                    {{ multipliedNumbers }}
                </span>
            </div>
            
        </div>
    </div>

    <!-- kata 4 -->
    <div class="mx-8 mb-4 p-4 bg-neutral-950 rounded-lg border-4 border-double border-indigo-400" :class="{'border-rose-400': !changedCharactersCorrect}">
        <p class="text-gray-300">
            <span class="font-bold text-indigo-300">Kata IV:</span>
            Implement a function called <span class="text-lime-300">characterQuotes()</span> 
            that takes in <span class="text-orange-300">characters</span> and returns a new array just the name and quote property of each object.
            <br/>
            Use <span class="text-lime-300">map()</span> to transform each object.

            <!-- Implement a function that takes an array of objects and returns a new array with just the name and quote property of each object. -->
        </p>
        <div class="pt-3">
            <span class="text-lime-300">
                characterQuotes(
                    <span class="text-orange-300">characters</span>
                )
            </span>
            <span class="pl-3 text-gray-500">
                // [{"name": '', "quote": ''},{"name": '', "quote": ''},{"name": '', "quote": ''},{"name": '', "quote": ''},{"name": '', "quote": ''}] 
            </span>
            <div>
                <span v-if="changedCharactersCorrect" class="text-lime-500 font-bold text-xl">
                    ✓
                </span>
                <span v-else class="text-rose-500 font-bold text-xl">
                    ✗
                </span>
                <span :class="{'underline decoration-dotted decoration-2 decoration-rose-500': !changedCharactersCorrect}">
                    {{ changedCharacters }}
                </span>
            </div>
            
        </div>
    </div>

    
    <!-- kata 5 -->
    <div class="mx-8 mb-4 p-4 bg-neutral-950 rounded-lg border-4 border-double border-indigo-400" :class="{'border-rose-400': !filteredWordsCorrect}">
        <p class="text-gray-300">
            <span class="font-bold text-indigo-300">Kata V:</span>
            Implement a function called <span class="text-lime-300">filterWords()</span> 
            that takes in an array of words 
            and returns a new array with only the words that have a length greater than 6.
            <br/>
            Use <span class="text-lime-300">filter()</span> to filter out the words that have a length less than or equal to 6.
        </p>
        <div class="pt-3">
            <span class="text-lime-300">
                filterWords(
                    <span class="text-orange-300">words</span>
                )
            </span>
            <span class="pl-3 text-gray-500">
                // {{ filteredWordsExpected }}
            </span>
            <div>
                <span v-if="filteredWordsCorrect" class="text-lime-500 font-bold text-xl">
                    ✓
                </span>
                <span v-else class="text-rose-500 font-bold text-xl">
                    ✗
                </span>
                <span :class="{'underline decoration-dotted decoration-2 decoration-rose-500': !filteredWordsCorrect}">
                    {{ filteredWords }}
                </span>
            </div>
            
        </div>
    </div>

    <!-- kata 6 -->
    <div class="mx-8 mb-4 p-4 bg-neutral-950 rounded-lg border-4 border-double border-indigo-400" :class="{'border-rose-400': !completedItemsCorrect}">
        <p class="text-gray-300">
            <span class="font-bold text-indigo-300">Kata VI:</span>
            Implement a function called <span class="text-lime-300">filterCompleted()</span> 
            that takes in an array of <span class="text-orange-300">todoItems</span> 
            and returns a new array with just the objects that have a property called "completed" set to true.
            Create a new property on each object called "ezpz" that is a Boolean. Mark "ezpz" true if the task contains 2 or less words.
            <br/>
        </p>
        <div class="pt-3">
            <span class="text-lime-300">
                filterCompleted(
                    <span class="text-orange-300">todoItems</span>
                )
            </span>
            <span class="pl-3 text-gray-500">
                // {{ completedItemsExpected }}
            </span>
            <div>
                <span v-if="completedItemsCorrect" class="text-lime-500 font-bold text-xl">
                    ✓
                </span>
                <span v-else class="text-rose-500 font-bold text-xl">
                    ✗
                </span>
                <span :class="{'underline decoration-dotted decoration-2 decoration-rose-500': !completedItemsCorrect}">
                    {{ completedItems }}
                </span>
            </div>
            
        </div>
    </div>

    <!-- kata 7 -->
    <div class="mx-8 mb-4 p-4 bg-neutral-950 rounded-lg border-4 border-double border-indigo-400" :class="{'border-rose-400': !squaredNumbersCorrect}">
        <p class="text-gray-300">
            <span class="font-bold text-indigo-300">Kata VII:</span>
            Implement a function called <span class="text-lime-300">squareAllFilterEvensAndAddAll()</span> 
            that takes in <span class="text-orange-300">totallyOriginalNumbers</span> 
            and returns a new array with each number squared. Filter out all the even numbers. Then add all of the numbers together.
        </p>
        <div class="pt-3">
            <span class="text-lime-300">
                squareAllFilterEvensAndAddAll(
                    <span class="text-orange-300">totallyOriginalNumbers</span>
                )
            </span>
            <span class="pl-3 text-gray-500">
                // {{ squaredNumbersExpected }}
            </span>
            <div>
                <span v-if="squaredNumbersCorrect" class="text-lime-500 font-bold text-xl">
                    ✓
                </span>
                <span v-else class="text-rose-500 font-bold text-xl">
                    ✗
                </span>
                <span :class="{'underline decoration-dotted decoration-2 decoration-rose-500': !squaredNumbersCorrect}">
                    {{ squaredNumbers }}
                </span>
            </div>
        </div>
    </div>

    <!-- kata 8 -->
    <div class="mx-8 mb-4 p-4 bg-neutral-950 rounded-lg border-4 border-double border-indigo-400" :class="{'border-rose-400': !longestWordCorrect}">
        <p class="text-gray-300">
        <span class="font-bold text-indigo-300">Kata VIII:</span>
        Implement a function called <span class="text-lime-300">getLongestWord()</span>
        that takes in <span class="text-orange-300">longWords</span>
        and returns the longest word in the array.        
        </p>
        <div class="pt-3">
        <span class="text-lime-300">
            longestWord(
            <span class="text-orange-300">longWords</span>)
        </span>
        <span class="pl-3 text-gray-500">
            // {{ longestWordExpected }}
        </span>
        <div>
            <span v-if="longestWordCorrect" class="text-lime-500 font-bold text-xl">
            ✓
            </span>
            <span v-else class="text-rose-500 font-bold text-xl">
            ✗
            </span>
            <span :class="{'underline decoration-dotted decoration-2 decoration-rose-500': !longestWordCorrect}">
            {{ longestWord }}
            </span>
        </div>
        </div>
    </div>

</template>

<style lang="postcss" scoped>
</style>