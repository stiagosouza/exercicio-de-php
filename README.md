<!DOCTYPE html>

<html lang="pt-br">
<head>
        <meta charset="UTF-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
            <title>Curso de PHP UTD</title>
        <!-- CSS only -->
       
    <link rel="stylesheet" type="text/css" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.css" >

    <style>
        *{
        margin:0;
        padding:0;
        box-sizing: border-box;
        }
        body{
            
            width: 100%;
            height: 100%; 
            }
        .menu{
            position: fixed;
            width: 100%;
            height:70px;
            background-color: rgb(255, 255, 255);
            top: -10px;
    }     
       
        .fd{
            float:right;
            margin-right:10px;
            padding: auto;
            width: 100%;
            height: 190px;
        }
      
        .cadastro {
            float:left;
            margin-left:auto;
            width: 100%;
            margin-top:200px; 
        }
        #table {
            width: 80%;
            height: 170px;
            margin-left:110px;
            color:#708090;
            background:#ADD8E6;]
            border: 2px solid #000000;
        }
        th{
            font-size:25px;
            color:black;
            background:#1E90FF;
        }
        tr{
            text-align:center;
        }
        .un{
            
            width: 20%;
            height: 25px;
            background-color: #D3D3D3;
            border: 2px solid #4F4F4F;
            border-radius:5px;
        
        }
        
        label{
            margin-top: 1rem;
            font-style: oblique;
            text-align: center;
            font-size: 20px;
        }
       .but{
            width: 70px;
            cursor: pointer;
            background-color:#4169E1;
            padding: 5px;
            margin-top:8px;
            font-size:15px;
            color:#F0F8FF;
        }   
        h3{
            font-size:35px;
            color:#F0F8FF;
            background-color:#4169E1;
        }
       
    </style>
   
</head>
<body>
   
<header>
  <main class="menu"> 
      <div>
          <img class="fd" src="https://i.imgur.com/nX90vOa.pnga" alt="folder">
      </div>
   
   </main>
</header>
<br><br><br><br>
    <div class="cadastro">
        <!--Questão 01-->
        <div >
            <table id="table" border=2 >
                <tr>
                    <th> Nome </th>
                    <th> Idade </th>
                    <th> Nascimeto </th>
                    <th> Cidade </th>
                    <th> UF </th>
                    <th> Endereço</th>
                </tr> 
                <tr>
                    <td> Tiago Martins</td>
                    <td> 31</td>
                    <td> 1990</td>
                    <td> Fortaleza</td>
                    <td> CE</td>
                    <td> Trvs S J Batista</td>
                </tr> 
                <tr>
                    <td> Tiago Martins</td>
                    <td> 31</td>
                    <td> 1990</td>
                    <td> Fortaleza</td>
                    <td> CE</td>
                    <td> Trvs S J Batista</td>
                </tr> 
                <tr>
                    <td> Tiago Martins</td>
                    <td> 31</td>
                    <td> 1990</td>
                    <td> Fortaleza</td>
                    <td> CE</td>
                    <td> Trvs S J Batista</td>
                </tr> 
            </table >

            <br><br>
        
        </div>
        
              <!--Questão 02-->
              
        	<h3 align="center">Cálculo de Média</h3>
		<div >
            <br><br><br>
		    <form action="" method="GET">
                    <p>
                	<input  type="text" name="v1" placeholder=" Digite um número" >
                    </p>
                    <p>
                	<input type="text" name="v2"  placeholder=" Digite um número">
                	</p>
                	<p>
                	<input type="texte" name="v3"  placeholder=" Digite um número">
                	</p>
                   <div class="butao"> 
                        <input class="but" type="submit" value="Calcular" >
                        <input class="but" type="reset" value="Limpar">
                    </div>
                   <?php
                      if(isset($_POST['calcular'])){
                          $nota = array($_POST['v1'],$_POST['v2'],$_POST['v3']);
                          $num_position = count($notas);

                          $soma= 0;
                           for ($i = 0;$i <=  $num_position;$i++){
                               $soma += @$notas[$i];
                           }
                          echo $soma;
                      }
                    
                    ?> 
            </form>       
		</div> 
        <br><br><br><br>
            <!--Questão 03-->
      <form>               
            <label  for="User Name" type="text" ><i class="fa fa-user-circle" aria-hidden="true"></i>Usuário</label>
            <br>
            <input class="un" placeholder=" Email ou CPF " type="text" id="username" name="username" >
            <br>
            <label for="pass">Senha </label>
            <br>
            <input class="un" placeholder="Digite a Senha" type="text" type="password" id="passname" name="password" minlength="6" required><br>
            <input class="but" type="submit" value="Entrar" >            
      </form>    
      

      <br><br><br><br>
            <!--Questão 04-->

      <form method="POST">
            <label>Linhas:</label>
            <input type="text" name="linhas">
            <label>Colunas: </label>
            <input type="text" name="colunas">
            <input class="but" type="Submit" value="Gerar">
      </form>

        <?php
            $linhas = isset($_POST['linhas']) ? $_POST['linhas'] : -1;
            $colunas = isset($_POST['colunas']) ? $_POST['colunas'] : -1;
            if($linhas > 0 && $colunas > 0)
                echo "Criado uma tabela de " . $linhas . " linhas por " . $colunas . " colunas";
              
            echo "<table border='1' cellpading='10' cellspacing='10' style='border:1px solid #000; width:" . ($colunas * 100) . "px;height:" . ($linhas * 50). "px;'>";
            $l = 0;
            while($l < $linhas)
            {
                $l++;
                echo "<tr>";
                $c = 0;
                while ($c < $colunas)
                {
                    $c++;
                    echo "<td style='border:'1rem;'>" . $l . "" . $c . "</td>";     
                }
                echo "</tr>";   
            }
            echo "</table>";
        ?>

            <br><br><br>

            <input class="but" type="submit" value="enviar">
            <input class="but" type="reset" value="Limpar">

    </div> 
</div>  
</body>
</html>
