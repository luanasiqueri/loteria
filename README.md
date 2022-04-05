# Projeto Loteca
Este é um projeto de um simulador de loteria, onde o usuário digita seis números e é realizado um sorteio de seis números aleatórios. 
No final, é verificado os acertos.

## Tecnologias Utilizadas
- **HTML**: Estrutura do site
- **CSS**: Estilização do site
- **JS**: Funções do site
- ~~BootStrap~~: Não foi utilizado

### Melhorias Possíveis
1. [x] Subir para GitHubPages
2. [ ] Alterar os Alerts
3. [ ] Utilizar o BootStrap
4. [ ] Deixar responsivo

#### Disponibilizado em 
  [GitHubPage](https://luanasiqueri.github.io/loteria/)
  
  
  
### Prints da Tela

| ID | Primeira tela | Segunda tela |
|----|---------------|--------------|
| 1  | Loteca limpa  | Loteca preenchida |
| 2  | ![tela loteca não preenchida](https://user-images.githubusercontent.com/100212689/161781598-bca30b5f-e3b6-49d1-a68c-050adddb1aab.png) | ![tela loteca preenchida](https://user-images.githubusercontent.com/100212689/161781848-29e1c70d-e301-42e1-b1a4-d5cda8f9a65d.png)|


##### Função Principal
```
function sorteio(){
    if(numEsco.length==6){
        var cont = 0
        numSort = []
        while(cont<6){
            let num = Math.random()*60
            num = Math.ceil(num)

            if(!numSort.includes(num)){
                numSort[cont] = num 
                console.log(numSort)
                cont++
            }
        }
        document.getElementById("sorteados").innerHTML = numSort
        contAcertos()
    }else{
        alert("É necessário digitar os 6 números antes do sorteio")
    }
    
}

function getValor(valor, pos){
    valor  = Number(valor)
    
    if(valor<=0 || valor>60){
        alert("Número inválido, digite um númmero entre 1 e 60")
        document.getElementById(`num${pos+1}`).value = ""
    } else if(numEsco.includes(valor)){
        alert("Número repetido, escolha outro número!")
        document.getElementById(`num${pos+1}`).value = ""
    }else{
        numEsco[pos] = valor
        console.log(numEsco)

    }
    
}


function contAcertos(){
    let contA = 0
    numEsco.forEach(function(value, index){
        if(numSort.includes(value)){    
            contA = contA+1
        }      
    })

    document.getElementById("acertos").innerHTML = contA
}
```

##### Comando Git
para iniciar o projeto
```
git init

```
