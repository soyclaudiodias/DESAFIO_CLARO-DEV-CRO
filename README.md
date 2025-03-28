# DESAFIO_CLARO-DEV-CRO
Soluções para o desafio de front-end da Claro, envolvendo JavaScript, CSS e HTML. As tarefas incluem modificar texto, alterar estilos, reordenar elementos e adicionar novos links e cards usando manipulação DOM. Foco em boas práticas de desenvolvimento e seleção de elementos.

## Exercício 01
<p>Altere o texto do menu “Atendimento” (circulado em amarelo) para texto “Teste CRO”:</p>
<ul>
  <li>Use seletores Javascript para alterar o texto do último botão de nome “Atendimento” para “Teste-CRO”;</li>
  <li>Após o código ser testado, salve o código abaixo:</li>
</ul>

```
document.querySelectorAll('.mdn-Text').forEach((valor) => {
    if (valor.textContent.trim() === "Atendimento") {
        valor.textContent = "Teste-CRO";
    }
});
```
### Antes:
![www claro com br_](https://github.com/user-attachments/assets/65c6422d-52b5-4df0-94db-18c86e520b42)
### Depois:
![www claro com br_ (1)](https://github.com/user-attachments/assets/aae63409-bfcd-4c3e-88a5-e75946a056c5)

## Exercício 02
<p>Rolando a página para baixo, encontre a seção de cards de “Autoatendimento”, faça as seguintes alterações no card circulado em amarelo:</p>
<ul>
  <li>Alterar o background do card “Consumo de internet” para cor #ffc722;</li>
  <li>Alterar a cor dos ícones do card “Consumo de internet” para cor #000;</li>
  <li>Após o código ser testado, salve o código abaixo:</li>
</ul>
<p>Obs. Preferível em CSS;</p>

```
let card = document.querySelectorAll('.cms-content-Shortcut.mdn-Shortcut.cms-Shortcut-title.mdn-Shortcut--secondary');

if (card.length >= 3) {
    card[1].style.backgroundColor = "#ffc722";
    let icone = card[1].querySelector('.mdn-Icon-consumo');

    if (icone) {
        icone.style.color = "#000";
    }
}
```
### Antes:
![www claro com br_ (2)](https://github.com/user-attachments/assets/4ec72fa8-ef54-4f1e-b892-fc063adf95f7)
### Depois:
![www claro com br_ (3)](https://github.com/user-attachments/assets/ad0d8b2e-fae6-4217-897f-968835f792cf)

## Exercício 03
<p>Rolando a página para baixo, encontre a seção de cards de “Autoatendimento”, faça as seguintes alterações nos cards circulados em amarelo:</p>
<ul>
  <li>Altere as posições entre os cards “Ativar chip pré-pago” e “Acompanhar portabilidade”, passando o card “Acompanhar portabilidade” para frente do card “Ativar chip pré-pago”:</li>
  <li>Após o código ser testado, salve o código abaixo:</li>
</ul>

```
var lis = document.querySelectorAll('li.cms-ShortcutGroup-list-item');
var temp = lis[3].innerHTML
lis[3].innerHTML = lis[4].innerHTML;
lis[4].innerHTML = temp;
```
### Antes:
![www claro com br_ (4)](https://github.com/user-attachments/assets/62b574b7-af31-4ea7-8665-f844297331a3)
### Depois:
![www claro com br_ (5)](https://github.com/user-attachments/assets/b0b14bbe-4713-49b0-90ca-7586c0ab8560)

## Exercício 04
<p>Faça uma cópia do card “Suporte técnico”, repetindo todas as funcionalidades como link, click e formato. Em seguida adicione está copia na primeira posição, antes do card “2ª via da fatura”;</p>
<ul>
  <li>Após o código ser testado, salve o código abaixo:</li>
</ul>
Obs. Essa tarefa deve ser feita necessariamente em Javascript, tanto a copia quanto as funcionalidades.
<p>

```
let elementos = document.querySelectorAll('.cms-content-Shortcut.mdn-Shortcut.cms-Shortcut-title.mdn-Shortcut--secondary');

let suporteTecnicoCard = Array.from(elementos).find(element => element.textContent.includes("Suporte técnico"));
let segundoCard = Array.from(elementos).find(element => element.textContent.includes("2ª via da fatura"));

if (suporteTecnicoCard && segundoCard) {
    let novoCard = suporteTecnicoCard.cloneNode(true);
    segundoCard.parentNode.insertBefore(novoCard, segundoCard);

    let container = segundoCard.parentNode;
    novoCard.style.marginRight = "8px";

    novoCard.style.backgroundColor = "#fff";
    novoCard.style.borderRadius = "8px";
    novoCard.style.padding = "10px";
    novoCard.style.boxShadow = "0px 2px 4px rgba(0, 0, 0, 0.1)";

    let textoCard = novoCard.querySelector('.cms-Shortcut--texts');
    let iconeCard = novoCard.querySelector('.mdn-Icon-chave-combinada-fenda');

    if (textoCard)
        textoCard.style.color = "#000";
    if (iconeCard) {
        iconeCard.style.color = "#DA291C";
        iconeCard.style.display = "block";
        iconeCard.style.visibility = "visible";
        iconeCard.style.opacity = "1";
        iconeCard.style.fontSize = "24px";
    }
}
```
⚠️ Não respeita a responsabilidade a partir do tamanho 425px.

### Antes:
![www claro com br_ (6)](https://github.com/user-attachments/assets/a5e36c57-f735-4fa8-97fb-cf3e0556b731)
### Depois:
![www claro com br_ (7)](https://github.com/user-attachments/assets/ab9e558b-7a4b-48cf-96ee-8dc0700892d0)

## Exercício 05
<p>Volte para o header da página:</p>
<ul>
  <li>Clique na seção de Serviços Digitais e deixe apenas um link, remova todas os outros. O link que deve criar será o “Claro Educação” e o seu direcionamento é para essa URL: “https://www.claro.com.br/servicos/saude-e-bem-estar”</li>
  <li>Após o código ser testado, salve o código abaixo:</li>
</ul> 
<p>Obs. Essa tarefa deve ser feita necessariamente em Javascript, tanto a copia quanto as funcionalidades. Não pode deixar o link atual, precisa criar um do zero</p>

```
document.querySelectorAll('.mdn-Text').forEach((menu) => {
    if (menu.textContent.trim() === "Serviços Digitais") {
        document.querySelectorAll(".mdn-Menu-subMenu-list").forEach((submenu) => {
            let items = submenu.querySelectorAll(".mdn-LinkList-item"); 

            items.forEach((item, index) => {
        		if (index == 0) {
        			document.querySelectorAll('.mdn-LinkList-item a').forEach((valor) => {
                    	if (valor.textContent.trim() === "Educação") {
                            valor.textContent = "Claro Educação";
                            valor.href = "https://www.claro.com.br/servicos/saude-e-bem-estar";
                        }
                    });
        		}
            	if (index > 0) {
                	item.remove();
            	}
            });
        });
    }
});
```
⚠️ Só aplicado quando a seção está selecionada.

### Antes:
![www claro com br_ (8)](https://github.com/user-attachments/assets/1376a332-4b30-43cd-baf5-ab141277f204)
### Depois:
![www claro com br_ (9)](https://github.com/user-attachments/assets/3c0939a9-31f4-46cb-a1e4-f782f11086f5)

## Exercício 06
<p>Volte para o header da página:</p>
<ul>
  <li>Clique na seção de Combos e estilize no mesmo modelo dos cards que estão em “Contrate” (botão amarelo canto direito do header da página)</li>
</ul> 
<p>Obs. Essa tarefa deve ser feita necessariamente em Javascript, tanto a copia quanto as funcionalidades.</p>

```
document.querySelectorAll('.mdn-Text').forEach((menu) => {
    if (menu.textContent.trim() === "Serviços Digitais") {
        const menu = document.querySelector('.mdn-Menu-subMenu-list');
        menu.innerHTML = '';

        const itemNames = [
            { name: "Combos sugeridos", link: "https://www.claro.com.br/combos" },
            { name: "Escolha sua combinação", link: "https://planos.claro.com.br/cobertura" }
        ];

        itemNames.forEach((item, index) => {
            const li = document.createElement('li');
            li.classList.add('mdn-Menu-subMenu-list-item');

            const div = document.createElement('div');
            div.classList.add('mdn-Menu-shortcut');

            const ul = document.createElement('ul');
            ul.classList.add('cms-Menu-shortcut-list', 'cms-Menu-shorcut-list-highlight');

            const listItem = document.createElement('li');
            listItem.classList.add('cms-Menu-shortcut-list-item');

            const link = document.createElement('a');
            link.classList.add('cms-Link', 'gtm-element-event', 'cms-Menu-shortcut-list-item-link');
            link.setAttribute('href', item.link);
            link.setAttribute('title', `Acesse ${item.name}`);
            link.setAttribute('aria-label', `Acesse ${item.name}`);

            const buttonText = document.createElement('p');
            buttonText.classList.add('mdn-Text');
            buttonText.textContent = item.name;
            buttonText.style.margin = '15% 0';
            link.appendChild(buttonText);

            listItem.appendChild(link);
            ul.appendChild(listItem);
            div.appendChild(ul);
            li.appendChild(div);

            if (index === 1) {
                link.style.color = '#000';
                link.style.backgroundColor = '#fff';
            }

            menu.appendChild(li);
        });
    }
});
```
⚠️ Apresenta erro ao clical na seção "Combos" novamente. Foi utilizado parcialmente a IA neste exercício para tentar contornar o problema de remover um nó filho de um elemento que não é mais um filho válido, além de manipular o DOM (Document Object Model) para criar os novos itens de menu e aplicar as mesmas classes e estrutura da opção 'Contrate'.

### Antes:
![www claro com br_ (10)](https://github.com/user-attachments/assets/bb75fc59-89cc-4fe4-a497-8ac846c16bf4)
### Depois:
![www claro com br_ (11)](https://github.com/user-attachments/assets/5aaf1173-11c3-478f-afad-f76bad3ac30a)
