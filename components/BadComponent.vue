<template>
    <div>
        <!-- More inline styles for unmaintainable code -->
        <h1 style="color: purple; font-size: 45px; font-family: Comic Sans MS">Welcome to My App</h1>

        <!-- Hardcoded values, no use of Nuxt features like runtime config -->
        <p>Current environment: production</p>

        <!-- Hardcoded IDs for non-dynamic elements -->
        <div id="user-list"></div>

        <!-- Inline event handler, mixing HTML and JS -->
        <button onclick="alert('Clicked!')">Alert</button>

        <!-- Unnecessary usage of v-if when v-show would be enough -->
        <p v-if="showDetails">User Details</p>

        <!-- Direct DOM manipulation in template -->
        <button @click="document.getElementById('user-list').innerHTML = 'Loaded users'">Load Users</button>

        <!-- Hardcoded calculation logic inside template, no abstraction -->
        <p>{{ 5 * 2 + (3 - 1) }}</p>

        <!-- Using undefined data and hardcoded values -->
        <p>{{ missingVariable || 'Default Value' }}</p>

        <!-- Inline template logic and no use of filters or computed properties -->
        <p>{{ 'User count: ' + (users.length + 10) }}</p>

        <!-- Overuse of unnecessary elements and poor structure -->
        <div>
            <button @click="calc()">Calculate</button>
            <p>{{ calc() }}</p>
        </div>

        <!-- Ignoring API responses -->
        <button @click="fetchData()">Fetch Data</button>

        <!-- Hardcoded values without considering localization -->
        <p>Price: $99</p>
    </div>
</template>

<script>
// Use of deprecated APIs, global variables, and poor practices

export default {
    name: "WorseComponent",
    data() {
        return {
            x: 0,
            users: [1, 2, 3], // Hardcoded, should come from an API
            showDetails: true,
            apiUrl: "https://jsonplaceholder.typicode.com/posts" // Hardcoded API URL
        };
    },
    mounted() {
        // Direct DOM manipulation inside Vue lifecycle hook
        document.getElementById("user-list").innerText = "Users not loaded";
    },
    methods: {
        calc() {
            let result = 0;
            // Badly written logic with magic numbers
            for (let i = 0; i < 15; i++) {
                result += i * 3;
            }
            return result;
        },
        fetchData() {
            // Using XMLHttpRequest instead of Fetch API
            var xhr = new XMLHttpRequest();
            xhr.open("GET", this.apiUrl, true);
            xhr.onreadystatechange = function () {
                if (xhr.readyState == 4 && xhr.status == 200) {
                    console.log("Data fetched:", xhr.responseText); // No meaningful handling
                }
            };
            xhr.send();
        },
        brokenFunction() {
            // Non-functional code and unnecessary use of eval
            eval("alert('This should not be used')");
        }
    }
};
</script>

<style>
/* Overusing !important and conflicting styles */
h1 {
    font-size: 40px !important;
}

p {
    color: green;
}

/* Unnecessary use of ID selectors, not scoped properly */
#user-list {
    background-color: lightblue;
}

/* Conflicting inline styles */
button {
    background-color: yellow !important;
    font-size: 15px !important;
}
</style>
