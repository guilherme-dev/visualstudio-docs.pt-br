---
title: Visão geral de cor e de fonte | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], font and color
- font and color control [Visual Studio SDK], editors
ms.assetid: 2203e4e7-8b7f-44ec-8884-6ff718d4f278
caps.latest.revision: 23
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 611620b0560563cfba41b302c3e8e3611ab5a7a8
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49888652"
---
# <a name="font-and-color-overview"></a>Visão geral de cor e de fonte
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Este tópico discute as configurações de fonte e cor do texto no [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] o ambiente de desenvolvimento integrado (IDE). Ele também apresenta os conceitos de categorias e itens de exibição e descreve como os VSPackages e o editor principal usam atributos de texto.  
  
## <a name="the-fonts-and-colors-property-page"></a>A página de propriedades de cores e fontes  
 Você pode gerenciar os atributos do texto exibido no [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] ambiente de desenvolvimento integrado (IDE) por meio de **fontes e cores** página de propriedades. Para localizar o **fontes e cores** página de propriedades na **ferramentas** menu, clique em **opções**. Expandir **ambiente**e, em seguida, clique em **fontes e cores**.  
  
## <a name="categories-and-display-items"></a>Categorias e itens de exibição  
 Fontes e cores são organizadas em **categorias** e **itens de exibição**.  
  
- Um **categoria** é um contêiner lógico ou funcional para um número de **itens de exibição**.  
  
   Uma lista de **categorias** está no **Mostrar configurações de** caixa de lista suspensa dos **fontes e cores** página de propriedades.  
  
- Um **Item de exibição** é uma entidade de texto bem definido como um comentário, uma cadeia de caracteres ou uma estrutura de controle que deve ser colorido quando exibidos.  
  
  Cada **Item de exibição** é definida exclusivamente dentro do **categoria** que o contém. Consequentemente, mais de um **categoria** pode ter um **Item de exibição** com o mesmo nome.  
  
## <a name="vspackage-control-of-fonts-and-colors"></a>VSPackage de controle de fontes e cores  
 O [!INCLUDE[vsipsdk](../includes/vsipsdk-md.md)] permite que os VSPackages para:  
  
- Definir fontes e cores **categorias**.  
  
- Especificar as fontes e cores usadas para apresentar **itens de exibição**.  
  
- Interagir com o **fontes e cores** página de propriedades.  
  
- Agregar vários **categorias** em grupos.  
  
- Manter as alterações nas configurações padrão.  
  
  Há duas maneiras de interagir com as seleções de fonte e cor dentro do [!INCLUDE[vsipsdk](../includes/vsipsdk-md.md)].  
  
- Uma maneira é conhecida como *coloração de sintaxe*. Ele é usado por um VSPackage que personaliza existente [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] editor para implementar um serviço de linguagem e criar uma fonte de editor.  
  
   Somente um **categoria** dá suporte a esse mecanismo, ou seja, o **Editor de texto**.  
  
- Uma alternativa mais geral é compatível com todos os outros **categorias** e componentes de interface do usuário que não seja o editor de código-fonte ao exibir texto. Para obter mais informações, consulte <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorDefaultsProvider>.  
  
## <a name="core-editor-text-settings"></a>Configurações de Editor principal do texto  
 Configurações de fonte e cor para o editor de núcleo de um objeto de serviço de linguagem são governadas pela **texto EditorCategory** encontrado na **Mostrar configurações de** caixa suspensa do **fontes e cores** página de propriedades.  
  
 Ao trabalhar com editores, você deve usar a fonte especializada e o mecanismo de controle de cor que o serviço de linguagem fornece para controlar e estender os **Editor de texto** configurações. O mecanismo é conhecido como *coloração de sintaxe* e fornece:  
  
- Uma técnica simplificada para gerenciar as fontes e cores dos itens de exibição.  
  
   Para obter mais informações, consulte <xref:Microsoft.VisualStudio.TextManager.Interop.IVsProvideColorableItems> e <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorableItem>.  
  
- Um mecanismo de colorização bem definidas e otimizada.  
  
   Para obter mais informações, consulte <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer>.  
  
- A capacidade de ambos usam itens de exibição interna dos **EditorCategory texto** e estendê-las.  
  
   Para obter mais informações, consulte [como: usar itens de coloração internos](../extensibility/internals/how-to-use-built-in-colorable-items.md) e [itens de coloração personalizados](../extensibility/internals/custom-colorable-items.md).  
  
- Persistência automática do atual estado de ambas as internas e personalizada exibir itens com o **Editor de texto** categoria.  
  
  Para obter mais informações sobre consulte de coloração de sintaxe [coloração de sintaxe em um serviço de linguagem herdado](../extensibility/internals/syntax-coloring-in-a-legacy-language-service.md).  
  
## <a name="see-also"></a>Consulte também  
 [Interfaces herdadas no Editor](../extensibility/legacy-interfaces-in-the-editor.md)   
 [Coloração de sintaxe em um serviço de linguagem herdado](../extensibility/internals/syntax-coloring-in-a-legacy-language-service.md)

