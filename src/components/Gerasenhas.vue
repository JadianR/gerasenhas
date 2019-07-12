<template>
    <div class="principal">

        <span class="titulo">Gerador de Senhas</span>
        <br><br>
        
        <div class="slider">
            <input type="text" id="camposenha" placeholder="Senha Gerada"><br><br>
            <div id="tamanho">Tamanho: {{tamanho}}</div>
            <input type="range" min="8" max="26" id="slide" name="slide" v-model="tamanho"><br><br>
            
            <button type="button" class="btn btn-info" @click="gerarsenha()">Gerar Senha</button>
            <br><br>
        </div>

        <div class="marcadores">
           
            <select v-model="escolha">
                <option v-for="(op,indice) in opcoes" :key="indice">
                    {{op.descricao}}
                </option>
            </select>
            
        </div>   

    </div>
</template>

<script>
export default {
    name: 'Gerasenhas',
    data(){
        return {
            tamanho: 8,
            senha: "",
            escolha: "Maiúsculas",
            Maiusculas: 'ABCDEFGHIJKLMNOPQRSTUVWXYZ',
            Minusculas: 'abcdefghijklmnopqrstuvwxyz',
            Especiais: '!@#$%&*(?+_-',
            Numeros: '0123456789',
            MaiusculasMinusculas: 'aAbBcCdDeEfFgGhHiIjJkKlLmMnNoOpPqQrRsStTuUvVwWxXyYzZ',
            MaiusculasNumeros: '0A1B2C3D4E5F6G7H8I9J0K1L2M3N4O5P6Q7R8S9T0U1V2W3X4Y5Z6',
            MinusculasNumeros: '0a1b2c3d4e5f6g7h8i9j0k1l2m3n4o5p6q7r8s9t0u1v2w3x4y5z6',
            MaiusculasEspeciais: '!A@B#C$D&E*F|G\H?I#J!#K(L£M¢N@O!P#Q%R*S?T¢U£V|W\X?Y!Z', 
            MinusculasEspeciais: '!a@b#c$d&e*f|g\h?i#j%$k#@l£m¢n@o!p#q%r*s?t¢u£v|w#x?y!z',
            NumerosEspeciais: '0!1@2#3$4%5)6&7*8(9?+_-',
            CaracteresAleatorios: '0A@B1C!D2EaF3G@H4IbJ5K#L6McN7O$P8QdR9S&T0UeV1W*X2YfZ3A|B4CgD5E#@F6GhH7I?J8KiL9M#N0O%P1QjR2S%$T3UkV4W(X5YlZ6A£B7CmD8E¢F9GnH0I@J1KoL2M!N3OpP4Q#R5SqT6U%V7WrX8Y*Z9AsB0C?D1EtF2G¢H3IuJ4K£L5MvN6O|P7QwR8S\T9UxV0W?X1YyZ2!3z4',
            opcoes: [
                {descricao: 'Maiúsculas'},
                {descricao: 'Minúsculas'},
                {descricao: 'Caracteres Especiais'},
                {descricao: 'Números'},
                {descricao: 'Maiúsculas e Minúsculas'},
                {descricao: 'Maiúsculas e Números (0-9)'},
                {descricao: 'Minúsculas e Números (0-9)'},
                {descricao: 'Maiúsculas e Caracteres Especiais'},
                {descricao: 'Minúsculas e Caracteres Especiais'},
                {descricao: 'Números e Caracteres Especiais'},
                {descricao: 'Tente Outras Possibilidades :)'}
                
            ]
        }
    },

    methods: {
        gerarsenha(){
            var resultado = '';
            if(this.escolha == 'Maiúsculas') {
                for(let indice = 1; indice <= this.tamanho; indice++){	
					var contador = Math.floor((Math.random()*this.Maiusculas.length)+0);
					resultado+= this.Maiusculas.charAt(contador);
                    this.senha = resultado;   
                       
                }
            }

            else if(this.escolha == 'Minúsculas') {
                for(let indice = 1; indice <= this.tamanho; indice++){	
					var contador = Math.floor((Math.random()*this.Minusculas.length)+0);
					resultado+= this.Minusculas.charAt(contador);
                    this.senha = resultado;    
                    
                }
            }

            else if(this.escolha == 'Caracteres Especiais') {
                 for(let indice = 1; indice <= this.tamanho; indice++){	
					var contador = Math.floor((Math.random()*this.Especiais.length)+0);
					resultado+= this.Especiais.charAt(contador);
                    this.senha = resultado;    
                    
                }
            }

            else if(this.escolha == 'Números') {
                 for(let indice = 1; indice <= this.tamanho; indice++){	
					var contador = Math.floor((Math.random()*this.Numeros.length)+0);
					resultado+= this.Numeros.charAt(contador);
                    this.senha = resultado;    
                    
                }
            }

            else if(this.escolha == 'Maiúsculas e Minúsculas') {
                 for(let indice = 1; indice <= this.tamanho; indice++){	
					var contador = Math.floor((Math.random()*this.MaiusculasMinusculas.length)+0);
					resultado+= this.MaiusculasMinusculas.charAt(contador);
                    this.senha = resultado;    
                    
                }
            }

            else if(this.escolha == 'Maiúsculas e Números (0-9)') {
                 for(let indice = 1; indice <= this.tamanho; indice++){	
					var contador = Math.floor((Math.random()*this.MaiusculasNumeros.length)+0);
					resultado+= this.MaiusculasNumeros.charAt(contador);
                    this.senha = resultado;    
                    
                }
            }

            else if(this.escolha == 'Minúsculas e Números (0-9)') {
                 for(let indice = 1; indice <= this.tamanho; indice++){	
					var contador = Math.floor((Math.random()*this.MinusculasNumeros.length)+0);
					resultado+= this.MinusculasNumeros.charAt(contador);
                    this.senha = resultado;    
                    
                }
            }

            else if(this.escolha == 'Maiúsculas e Caracteres Especiais') {
                 for(let indice = 1; indice <= this.tamanho; indice++){	
					var contador = Math.floor((Math.random()*this.MaiusculasEspeciais.length)+0);
					resultado+= this.MaiusculasEspeciais.charAt(contador);
                    this.senha = resultado;    
                    
                }
            }

            else if(this.escolha == 'Minúsculas e Caracteres Especiais') {
                 for(let indice = 1; indice <= this.tamanho; indice++){	
					var contador = Math.floor((Math.random()*this.MinusculasEspeciais.length)+0);
					resultado+= this.MinusculasEspeciais.charAt(contador);
                    this.senha = resultado;    
                    
                }
            }

            else if(this.escolha == 'Números e Caracteres Especiais') {
                 for(let indice = 1; indice <= this.tamanho; indice++){	
					var contador = Math.floor((Math.random()*this.NumerosEspeciais.length)+0);
					resultado+= this.NumerosEspeciais.charAt(contador);
                    this.senha = resultado;    
                    
                }
            }

            else if(this.escolha == 'Tente Outras Possibilidades :)') {
                 for(let indice = 1; indice <= this.tamanho; indice++){	
					var contador = Math.floor((Math.random()*this.CaracteresAleatorios.length)+0);
					resultado+= this.CaracteresAleatorios.charAt(contador);
                    this.senha = resultado;    
                    
                }
            }

            document.getElementById("camposenha").value = this.senha;
           
    
        }    
			
    }
        
}    
</script>

<style scoped>

.principal,
.titulo,
#camposenha,
select,
#tamanho{
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
    text-align: center;
    font-weight: bolder;
}

.principal{   
    margin: auto;   
}

.titulo {
    font-size: 25px;
}

#camposenha, #slide{
    width: 35%;
}

#slide{
    cursor:pointer;
}

button{
    border-radius: 2px;
    
}

#tamanho{
    color: black;
    font-weight: bolder;
}

#camposenha,
.principal{
    border-radius: 10px;
}
   
</style>
