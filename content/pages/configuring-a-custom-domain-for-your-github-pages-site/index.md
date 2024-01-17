<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Weighted Mean Calculator</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
        }
    </style>
</head>
<body>

<h1>Weighted Mean Calculator</h1>

<form id="weightedMeanForm">
    <label for="rating5">5 - Fully Satisfied:</label>
    <input type="number" id="rating5" name="rating5" min="0" step="1" value="0">

    <label for="rating4">4 - Satisfied:</label>
    <input type="number" id="rating4" name="rating4" min="0" step="1" value="0">

    <label for="rating3">3 - Somewhat Satisfied:</label>
    <input type="number" id="rating3" name="rating3" min="0" step="1" value="0">

    <label for="rating2">2 - Less Satisfied:</label>
    <input type="number" id="rating2" name="rating2" min="0" step="1" value="0">

    <label for="rating1">1 - Not Satisfied:</label>
    <input type="number" id="rating1" name="rating1" min="0" step="1" value="0">

    <button type="button" onclick="calculateWeightedMean()">Calculate</button>
</form>

<p id="result"></p>

<script>
    function calculateWeightedMean() {
        const rating5 = parseFloat(document.getElementById('rating5').value);
        const rating4 = parseFloat(document.getElementById('rating4').value);
        const rating3 = parseFloat(document.getElementById('rating3').value);
        const rating2 = parseFloat(document.getElementById('rating2').value);
        const rating1 = parseFloat(document.getElementById('rating1').value);

        const weight5 = 5;
        const weight4 = 4;
        const weight3 = 3;
        const weight2 = 2;
        const weight1 = 1;

        const totalWeight = rating5 * weight5 + rating4 * weight4 + rating3 * weight3 + rating2 * weight2 + rating1 * weight1;
        const totalRatings = rating5 + rating4 + rating3 + rating2 + rating1;
        const weightedMean = totalWeight / totalRatings;

        let verbalInterpretation = '';
        if (weightedMean >= 4.5) {
            verbalInterpretation = 'Fully Satisfied';
        } else if (weightedMean >= 3.5) {
            verbalInterpretation = 'Satisfied';
        } else if (weightedMean >= 2.5) {
            verbalInterpretation = 'Somewhat Satisfied';
        } else if (weightedMean >= 1.5) {
            verbalInterpretation = 'Less Satisfied';
        } else {
            verbalInterpretation = 'Not Satisfied';
        }

        document.getElementById('result').innerText = `Weighted Mean: ${weightedMean.toFixed(2)} - ${verbalInterpretation}`;
    }
</script>

</body>
</html>
