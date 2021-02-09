# Trabalhando com Templates (Facelets)
> Projeto a base de componentes Facelets a serem estruturados em páginas Java Server Faces (JSF)

[![ECLIPSE Version][ECLIPSE-image]][ECLIPSE-url]
[![Build Status][ECLIPSE-gpl]][ECLIPSE-url]
[![Downloads Stats][ECLIPSE-downloads]][ECLIPSE-url]

![](https://www.eclipse.org/eclipse.org-common/themes/solstice/public/images/logo/eclipse-foundation-white-orange.svg?w=283)  


Neste projeto foram criados arquivos separados para o cabeçalho, conteúdo e rodapé. Desta forma, utilizando as facilidades da **IDE ECLIPSE**, foram criados arquivos XHTML a partir do modelo *New Facelet Composition Page* para cada um deles, com a tag (`ui:composition`) a fim de injetá-los a um *Template* (Modelo) sempre que necessário.  

Para este propósito, foi estruturado um *template* denominado *New Facelet Template*, com a seguinte codificação:  

```sh
  <div id="header">
    <ui:insert name="header">
    	<!-- Header -->		
    </ui:insert>
  </div>

  <div id="content">
    <ui:insert name="content">
            <!-- Photo Grid -->		
    </ui:insert>
  </div>

  <div id="footer">
    <ui:insert name="footer">
    	<!-- Footer -->		
    </ui:insert>
  </div>
```  

  Foi utilizado a tag `ui:include`
  

Como diria um antigo mestre:
> Cedo ou tarde, você vai aprender, assim como eu aprendi, que existe uma diferença entre CONHECER o caminho e TRILHAR o caminho.

[ECLIPSE-image]: https://img.shields.io/eclipse-marketplace/v/notepad4e?style=plastic
[ECLIPSE-url]: https://www.eclipse.org/ide/
[ECLIPSE-downloads]: https://img.shields.io/eclipse-marketplace/dm/notepad4e?style=plastic
[ECLIPSE-gpl]: https://img.shields.io/eclipse-marketplace/l/notepad4e?style=plastic
[wiki]: https://github.com/seunome/seuprojeto/wiki