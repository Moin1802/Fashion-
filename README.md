# Fashion-
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Fabric & Lace Matcher</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 20px;
    }
    .container {
      display: flex;
      gap: 20px;
    }
    .dropdown, .suggestions {
      flex: 1;
    }
    select, button {
      width: 100%;
      padding: 10px;
      margin-top: 10px;
    }
    .suggestions {
      border: 1px solid #ccc;
      padding: 10px;
    }
    .product {
      margin-bottom: 10px;
    }
  </style>
</head>
<body>

<h1>Fabric & Lace Matcher</h1>

<div class="container">
  <!-- Fabric Selection -->
  <div class="dropdown">
    <h3>Select a Fabric:</h3>
    <select id="fabricSelect">
      <option value="cotton">Cotton</option>
      <option value="silk">Silk</option>
      <option value="chiffon">Chiffon</option>
      <option value="linen">Linen</option>
    </select>
    <button onclick="generateSuggestions()">Find Matching Laces</button>
  </div>

  <!-- Suggested Laces -->
  <div class="suggestions">
    <h3>Matching Laces:</h3>
    <div id="laceSuggestions">
      <p>Select a fabric to see suggestions.</p>
    </div>
  </div>
</div>

<script>
  const laceData = {
    cotton: [
      { name: "Embroidered Lace", color: "White" },
      { name: "Crochet Lace", color: "Ivory" }
    ],
    silk: [
      { name: "Beaded Lace", color: "Gold" },
      { name: "Velvet Lace", color: "Maroon" }
    ],
    chiffon: [
      { name: "Sequin Lace", color: "Silver" },
      { name: "Net Lace", color: "Peach" }
    ],
    linen: [
      { name: "Floral Lace", color: "Beige" },
      { name: "Cotton Lace", color: "Off-white" }
    ]
  };

  function generateSuggestions() {
    const fabric = document.getElementById("fabricSelect").value;
    const suggestions = laceData[fabric];

    const laceSuggestionsDiv = document.getElementById("laceSuggestions");
    laceSuggestionsDiv.innerHTML = ""; // Clear previous suggestions

    suggestions.forEach(lace => {
      const productDiv = document.createElement("div");
      productDiv.className = "product";
      productDiv.innerHTML = `<strong>${lace.name}</strong> - Color: ${lace.color}`;
      laceSuggestionsDiv.appendChild(productDiv);
    });
  }
</script>

</body>
</html>
