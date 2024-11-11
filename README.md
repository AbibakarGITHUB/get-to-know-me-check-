# get-to-know-me-check-
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>  
<body>
    <div id="app"></div>

    <script>
        // Model
        const model = {
            person: {
                name: "abibakar",
                last: "hussein",
                age: '22',
                hobby: "compatsport",
            },
            input: {
                name: "",
                last: "",
                age: "",
                hobby: ""
            }
        };

        let text = "";

        // Update view
        function updateView() {
            document.getElementById('app').innerHTML = /*HTML*/`
                <h1>Test how much do you know me!</h1>
                <h3>Fill here!</h3>
                <input type="text" placeholder="Enter the name" onchange="model.input.name = this.value">
                <input type="number" placeholder="Enter the age" onchange="model.input.age = this.value">
                <br>
                <input type="text" placeholder="Enter the last name" onchange="model.input.last = this.value">
                <input type="text" placeholder="Enter the hobby" onchange="model.input.hobby = this.value">
                <button onclick="clickBtn()">Click here</button>
                <div>${text}</div>
            `;
        }

        // Controller
        function clickBtn() {
            // Check input against model data
            if (
                model.input.name === model.person.name &&
                model.input.age === model.person.age &&
                model.input.last === model.person.last &&
                model.input.hobby === model.person.hobby
            ) {
                text = "Hei, Abibakar! You got it, yes you can, just do it!";
            } else {
                text = "That's not correct, try again!";
            }
            
            // Update the view to reflect the new message
            updateView();
        }

        // Initial update
        updateView();
    </script>
</body>
</html>
