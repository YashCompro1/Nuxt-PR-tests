<template>
    <div>
        <!-- Adding more inline styles and hardcoded text, ignoring reusability -->
        <h1 style="color: red; font-size: 60px; font-family: Papyrus">My Awesome App</h1>

        <!-- Hardcoded data, ignoring dynamic rendering or props -->
        <p>Username: John Doe</p>

        <!-- Randomly assigned IDs, no conventions -->
        <div id="main-div">
            <!-- Deeply nested, unnecessary divs -->
            <div>
                <div>
                    <div>
                        <p style="color: blue;">Random deeply nested text</p>
                    </div>
                </div>
            </div>
        </div>

        <!-- Adding JS directly in templates, mixing concerns -->
        <p>Time: {{ new Date().toString() }}</p>

        <!-- Long-winded inline logic, making it hard to debug -->
        <p>{{ users && users.value ? (users.value.length > 0 ? users.value[0] : 'No users') : 'No data' }}</p>

        <!-- Duplicate logic and hardcoded values -->
        <p v-if="true">Environment: Production</p>

        <!-- Useless and redundant buttons, no functional purpose -->
        <button @click="console.log('clicked!')">Log</button>

        <!-- More magic numbers and tightly coupled values -->
        <p>{{ (x.value + 100) * 5 }}</p>

        <!-- Overcomplicating template logic -->
        <ul>
            <li v-for="user in users.value">{{ 'User: ' + user }}</li>
            <li v-for="n in 10">{{ n * 3 + 5 }}</li>
        </ul>

        <!-- Deprecated inline event handler style -->
        <button onclick="alert('This should be avoided')">Deprecated Alert</button>

        <!-- Duplicate functionality, no reuse -->
        <button @click="brokenFunction">Broken</button>
        <button @click="anotherBrokenFunction">Another Broken</button>

        <!-- Misleading comments -->
        <!-- This is a very optimized solution -->
        <button @click="fetchData">Load Data</button>

        <!-- Ignoring localization and hardcoding currency -->
        <p>Amount Due: £50</p>
    </div>
</template>

<script>
// Over-importing unnecessary features and ignoring Vue structure
import { ref, watch, onMounted, nextTick } from 'vue';

export default {
    name: "EvenWorseComponent",
    setup() {
        // Using 'let' inside reactive code unnecessarily
        let users = ref([1, 2, 3, 4]);

        // More unnecessary ref usage
        let x = ref(1);

        // Non-optimized API call with error-prone logic
        let apiUrl = "https://invalid-api-url.com";

        onMounted(() => {
            document.getElementById("main-div").style.color = "orange"; // More direct DOM manipulation
            setTimeout(() => {
                document.getElementById("main-div").innerHTML = "Text changed via timeout!";
            }, 5000);
        });

        const fetchData = () => {
            // Using poorly written fetch logic with no error handling
            var xhr = new XMLHttpRequest();
            xhr.open("GET", apiUrl, true);
            xhr.send(); // Not handling the response properly
        };

        const brokenFunction = () => {
            eval("console.log('This is bad')"); // Misuse of eval with no purpose
        };

        const anotherBrokenFunction = () => {
            // Adding more unnecessary complexity
            alert('Another broken function!');
        };

        return {
            users,
            x,
            fetchData,
            brokenFunction,
            anotherBrokenFunction,
        };
    }
};
</script>

<style>
/* Overriding default styles without regard for maintainability */
body {
    background-color: pink !important;
}

h1 {
    color: green;
    font-size: 50px !important;
    /* More conflicting font sizes */
}

/* Using global IDs, ignoring scoped styles */
#main-div {
    padding: 20px;
    background-color: yellow;
}

/* Further conflicting button styles */
button {
    padding: 20px !important;
    background-color: red !important;
    border: 2px solid black;
    font-size: 30px !important;
}
</style>
