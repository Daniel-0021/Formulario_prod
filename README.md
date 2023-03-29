# Formulario_prod

  <style>

.form-group {
  display: flex;
  flex-direction: column;
  margin-bottom: 10px;
}

input,
select,
textarea {
  padding: 10px;
  font-size: 16px;
  border-radius: 5px;
  border: 1px solid #ccc;
  margin-top: 5px;
}

input[type="button"],
button[type="submit"] {
  background-color: #010401;
  color: white;
  padding: 10px 20px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  font-size: 16px;
  margin-top: 10px;
}

input[type="button"]:hover,
button[type="submit"]:hover {
  background-color: #000000;
}


p {
  font-size: 18px;
  margin-top: 20px;
}

#totalprice {
  font-weight: bold;
  font-size: 24px;
}

@media screen and (max-width: 600px) {
  .form-style-porto {
    max-width: 100%;
  }
}
  </style>

  <script> $(document).ready(function() {
    $(".form").validate({
      rules: {
        Tipo_material: {
          required: true
        },
        Qualidade_do_material: {
          required: true
        },
        Dimensão_Fita: {
          required: true
        },
        Metros_lineares: {
          required: true,
          number: true,
          min: 1,
          max: 20,
        },
        mensagem: {
          required: true
        }
      },
      messages: {
        Tipo_material: "Por favor, descreva o material.",
        Qualidade_do_material: "Por favor, selecione o tipo de material.",
        Dimensão_Fita: "Por favor, selecione a largura da fita.",
        Metros_lineares: {
          required: "Por favor, insira a quantidade de metros lineares.",
          number: "Por favor, insira um número válido.",
          min: "Por favor, insira um valor maior do que zero.",
          max: "Por favor, insira um valor menor ou igual a 20."
        },
        mensagem: "Por favor, descreva o seu produto."
      },
     
    });
  });

  </script>

    <script> 

    function Calcular_valor() {
      var Dimensão_Fita = document.getElementById("Dimensão_Fita").value;
      var Qualidade_do_material = document.getElementById("Qualidade_do_material").value;
      var Metros_lineares = document.getElementById("Metros_lineares").value;
      var Preço_fixo = 0
      var Valor_produto = 0; 

  switch (true) {
    case Dimensão_Fita === "22mm" && Qualidade_do_material === "Amadeirado":
      var Preço_fixo = 100;
      var Valor_produto = (Metros_lineares * Preço_fixo);
      break;
    case Dimensão_Fita === "35mm" && Qualidade_do_material === "Amadeirado":
      var Preço_fixo = 111;
      var Valor_produto = (Metros_lineares * Preço_fixo);
      break;
    case Dimensão_Fita === "64mm" && Qualidade_do_material === "Amadeirado":
      var Preço_fixo = 150;
      var Valor_produto = (Metros_lineares * Preço_fixo);
      break;
  }
  switch (true) {
    case Dimensão_Fita === "22mm" && Qualidade_do_material === "color":
      var Preço_fixo = 390;
      var Valor_produto = (Metros_lineares * Preço_fixo);
      break;
    case Dimensão_Fita === "35mm" && Qualidade_do_material === "color":
      var Preço_fixo = 300;
      var Valor_produto = (Metros_lineares * Preço_fixo);
      break;
    case Dimensão_Fita === "64mm" && Qualidade_do_material === "color":
      var Preço_fixo = 380;
      var Valor_produto = (Metros_lineares * Preço_fixo);
      break;
  }
  switch (true) {
    case Dimensão_Fita === "22mm" && Qualidade_do_material === "branco_tx":
      var Preço_fixo = 200;
      var Valor_produto = (Metros_lineares * Preço_fixo);
      break;
    case Dimensão_Fita === "35mm" && Qualidade_do_material === "branco_tx":
      var Preço_fixo = 210;
      var Valor_produto = (Metros_lineares * Preço_fixo);
      break;
    case Dimensão_Fita === "64mm" && Qualidade_do_material === "branco_tx":
      var Preço_fixo = 230;
      var Valor_produto = (Metros_lineares * Preço_fixo);
      break;
  }
  document.getElementById("Valor_produto").innerHTML = Valor_produto.toFixed(2);
}   
    </script> 



            <h2>Anuncie Categoria Fita de Bordas</h2>
    <div class="form-group">
      <label for="Tipo_material">Descreva o Material</label>
      <input type="text" id="Tipo_material" name="Tipo_material" >
      
    </div>

    <div class="form-group">
        <label for="Qualidade_do_material">Qual tipo de material ?</label>
        <select id="Qualidade_do_material" name="Qualidade_do_material"required>
          <option value="color">color</option>
          <option value="Amadeirado">Amadeirado</option>
          <option value="branco_tx">Branco Texturizado</option>
        </select>
      </div>

    <div class="form-group">
        <label for="Dimensão_Fita">Selecione  qual a largura da fita :</label>
        <select id="Dimensão_Fita" name="Dimensão_Fita"required>
          <option value="22mm">22mm</option>
          <option value="35mm">35mm</option>
          <option value="64mm">64mm</option>
        </select>
      </div>

    <div class="form-group">
      <label for="Metros_lineares">Quantos Metros de fita você irá anúnciar:</label>
      <input type="number" id="Metros_lineares" name="Metros_lineares" min="1" max= "20">
  
    </div>
    <input type="button" value="Calcular Preço" onclick="Calcular_valor()" /><br />
  </br>

  
  
  <p>Valor baseado nos valores inseridos acima de cada unidade :<br>
    R$ :<span id="Valor_produto"></span></p>

 
    <div class="form-group">
      <label for="mensagem">Descreva seu Produto:</label>
      <textarea id="mensagem" name="mensagem"></textarea>
    </div>
    <button type="submit">Enviar</button>
  </form>

