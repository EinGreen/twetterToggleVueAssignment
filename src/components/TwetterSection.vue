<template>
    <section v-bind:class="{'twetrList': isList, 'twetrCard': !isList}">
        <button @click="isList = !isList">Switch Look</button>
        <!-- Okay, tried to make a method, but it failed, then I figured out I could just set the variable of isList to the oppisite of whatever it is! -->
        <article v-for="tweet in tweets" v-bind:key="tweet.id" v-bind:class="{'listView': isList, 'cardView': !isList}">
            <!-- Note: Ids won't work since the for loop will create multiple articles with the same id, which isn't allowed! -->
            <!-- Figured it out! you can v-bind miltiple classes in an Object! -->
            <h3>{{ tweet.username }}</h3>
            <p class="twetrCon">{{ tweet.content }}</p>
            <p class="twetrDate">{{ tweet.dateCreated }}</p>
        </article>
    </section>
</template>

<script>
    export default {
        name: "twetter-section",
        data() {
            return {
                tweets: [
                    {
                        id: 1001,
                        username: "px4",
                        content: "pee pee poo poo",
                        dateCreated: "April 1, 2XXX"
                    }, 
                    {
                        id: 1002,
                        username: "barrybbenson",
                        content: "you like jazz?",
                        dateCreated: "April 1, 2XXX"
                    }, 
                    {
                        id: 1003,
                        username: "meaningfulusername",
                        content: "lorem lorem lorem why isn't this working?",
                        // for some reason, lorem won't work for me. This should be fine
                        dateCreated: "April 1, 2XXX"
                    }, 
                    {
                        id: 1004,
                        username: "lorem",
                        content: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Ex perspiciatis doloribus necessitatibus deserunt eos, officiis distinctio, harum quaerat iste, vero omnis. Nesciunt officiis officia voluptates repudiandae qui? Aperiam, eveniet tenetur.",
                        // Nevermind figured it out. JS doesn't give lorem so I copy and pasted this line from the HTML part of this component!
                        dateCreated: "Feb 28, 2020"
                    },
                    {
                        id: 1005,
                        username: "creativeusername",
                        content: "<insert creative twet here>",
                        dateCreated: "July 4, 1776"
                    }, 
                    {
                        id: 1006,
                        username: "uuuuuuhhhhhhh",
                        content: "um, okay. Let's see. Uh... uuuuhhhhh... hhhmmmm... memes",
                        dateCreated: "nani 69, 2014"
                    }, 
                    {
                        id: 1007,
                        username: "alex",
                        content: "I am the best user! I am cool! I am the greated!",
                        dateCreated: "April 1, 2021"
                        // if you haven't notice already, this is a joke. I'm not a simp
                    }, 
                    {
                        id: 1008,
                        username: "ranoutofcreativenames",
                        content: "okay, I have no idea what I'm doing and I'm pretty sure I just ran out of ideas for random twets. Yes I am still calling them twets for licensing purposes",
                        dateCreated: "April 17, 2021"
                    }, 
                    {
                        id: 1009,
                        username: "Ariana Grande",
                        content: "broken. from the bottom of my heart, i am so so sorry. i don't have words.",
                        dateCreated: "May 22, 2017"
                        // Yes, I did copy and paste an acual tweet from Ariana Grande that I found randomly on Google
                    }, 
                    {
                        id: 1010,
                        username: "10",
                        content: "10 10 10 10 10 10 10 10 10 10 10 10 10 10 10 10 10 10 10 10 10 10 10 10 10 10 10 10 10 10 10 10 10 10 10 10 10 10 10 10 10 10 10 10 10 10 10 10 10",
                        dateCreated: "Oct 10, 1010",
                    }
                    // Note to self: don't forget to bind a :key in the v-for loop function. Made Ids to put as keys
                    // Note to self 2: apparently vue doesn't like numbers that start with 00X. Weird
                ],
                isList: true,
                // ^This^ variable will show if the display will be in the form of a list or not
                // Note: there really should be a way to put comments on the same line of code somehow
            }
        },
    }
</script>

<style scoped>
    section {
        margin-left: 5px;
        margin-right: 5px;
        padding-left: 10px;
        padding-right: 10px;
        /* tried to fix it to make it pleasable, failed */
    }

    /* styling for List view */
    .twetrList {
        display: grid;
    }
    .listView {
        width: 100vw;
        border-bottom: 1px dotted black;
    }

    /* styling for Card view */
    .twetrCard {
        display: grid;
        justify-items: center;
        align-items: center;
        grid-template-columns: repeat(auto-fit, mixmax(100px, 1fr));
    }
    .cardView {
        min-width: 100px;
        max-width: 50vw;
        border: 1px solid black;
    }

    /* General Styling */
    .twetrCon {
        justify-self: start;
        text-align: start;
    }
    .twetrDate {
        justify-self: end;
        text-align: end;
    }

    /* Tried to fix button, kinda worked */
    button {
        display: fixed;
        width: 100px;
    }

    /* Note: sorta wish this was scss formate. I miss scss */
</style>