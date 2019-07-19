<html>

<head>
    <title>
        Growler
    </title>
</head>
<style>

</style>

<template>
    <div id="growler">
        <h1>Binding to text fields</h1>
        <h3>How to bind to an input field with a "text" type</h3>
        <input v-model="query" placeholder="Search...">
        <div>
            <p :style="{color: query}">
                Color: {{ query }}
            </p>
        </div>

        <h3>Add multiple lines!</h3>
        <p style="white-space: pre-line;"> {{ multiMessage }} </p>
        <textarea v-model="multiMessage" placeholder="Add multiple lines!">
        </textarea>

        <h1>Binding to checkboxes</h1>
        <h3>Binding to single value</h3>
        <label>
            <input type="checkbox" value="beers" v-model="searchIndexes">
            Beers
        </label>
        <br>
        <label>
            <input type="checkbox" value="breweries" v-model="searchIndexes">
            Breweries
        </label>
        <br>
        <small>
            selected: {{searchIndexes}}
        </small>

        <h1>Binding to Radio buttons</h1>
        <h3>Note: beers is selected right now. Change to null or breweries to change. </h3>
        <label>
            <input type="radio" value="beers" v-model="singleIndex">
            Beers
        </label>

        <label>
            <input type="radio" value="breweries" v-model="singleIndex">
            Breweries
        </label>

        <h1>Binding to Drop-down Lists</h1>
        <h3>Selecting single value</h3>
        <select v-model="singleIndex">
            <option value="beers">Beers</option>
            <option value="breweries">Breweries</option>
            <option value="distilleries">Distilleries</option>
            <option value="pubs">Pubs</option>
        </select>
        <small>Selected: {{ singleIndex }}</small>

        <h3>Selecting multiple values</h3>
        <select v-model="searchIndexes" multiple>
            <option value="beers">Beers</option>
            <option value="breweries">Breweries</option>
            <option value="distilleries">Distilleries</option>
            <option value="pubs">Pubs</option>
        </select>
        <small>Selected: {{ searchIndexes }}</small>

        <h1>Using the Trim Modifier (doesn't seem to work? Works the same way as regular query.)</h1>
        <input v-model.trim="trimmedQuery" placeholder="Search...">
        <p>{{ trimmedQuery }}</p>

        <h1>Lazily Binding Values</h1>
        <input v-model.number="numberQuery" placeholder="2+3=">
        <p>{{ numberQuery }}</p>

        <h1>Using the lazy Modifier (doesn't seem to work? Works the same way as regular query.)</h1>
        <!-- we can also do v-model.lazy.trim to remove white space -->
        <input v-model.lazy="lazyQuery" placeholder="2+3=">
        <p>{{ lazyQuery }}</p>
    </div>

    <!-- Instance of vue - view -->
    <!-- v-text - text directive -->
</template>
<script type="text/javascript" src="https://unpkg.com/vue"></script>
<script type="text/javascript" src="https://unpkg.com/axios/dist/axios.min.js"></script>
<script type="text/javascript">
    var growler = new Vue({
        el: '#growler',
        data: {
            query: '',
            trimmedQuery: '',
            lazyQuery: '',
            numberQuery: null,
            multiMessage: '',
            searchIndexes: [],
            singleIndex: 'beers'

        }
    });
</script>

</html>