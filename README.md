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

Depois é criado um arquivo XML (*mytags.taglib*) para mapear as TAG's, que são os arquivos que criamos, e atrelamos a um *NAMESPACE* a ser imbutido nas páginas **JSF**, na qual arquivamos no diretório `WEB-INF`;

Agora é necessário parametrizar para o *Servlet* que o nosso arquivo com as TAG's deve ser carregado ao iniciar o serviço, definindo o seguinte código:

```sh
<context-param>
  	<param-name>javax.faces.FACELETS_LIBRARIES</param-name>
  	<param-value>/WEB-INF/mytags.taglib.xml</param-value>
  </context-param>
```

Para concluir, inserimos as TAG's personalizadas a página XHTML senguindo a estrutura do *template* ficando como apresentado na codificação a seguir:

```sh
<html xmlns="http://www.w3.org/1999/xhtml"
	  xmlns:ui="http://xmlns.jcp.org/jsf/facelets"
	  xmlns:sn="http://mytags/supernovatech">

<ui:composition template="/template.xhtml">
	<ui:define name="header">
		<sn:cabecalho />	    
	</ui:define>
	<ui:define name="content">
	    <sn:conteudo />
	</ui:define>
	<ui:define name="footer">
	    <sn:rodape />
	</ui:define>
</ui:composition>
</html>
```


  

Como diria um antigo mestre:
> Cedo ou tarde, você vai aprender, assim como eu aprendi, que existe uma diferença entre CONHECER o caminho e TRILHAR o caminho.

[ECLIPSE-image]: https://img.shields.io/eclipse-marketplace/v/notepad4e?style=plastic
[ECLIPSE-url]: https://www.eclipse.org/ide/
[ECLIPSE-downloads]: https://img.shields.io/eclipse-marketplace/dm/notepad4e?style=plastic
[ECLIPSE-gpl]: https://img.shields.io/eclipse-marketplace/l/notepad4e?style=plastic
[wiki]: https://github.com/seunome/seuprojeto/wiki