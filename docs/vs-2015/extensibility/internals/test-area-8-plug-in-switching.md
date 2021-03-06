---
title: 'Área de teste 8: Alternância de plug-in | Microsoft Docs'
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
- source control [Visual Studio SDK], switching plug-ins
- source control plug-ins, switching
ms.assetid: 01370792-b5da-4e46-9ce2-7dd326587141
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f6be407cc89820cc466180077c90288d8b285f7e
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49296706"
---
# <a name="test-area-8-plug-in-switching"></a>Área de teste 8: alternância de plug-in
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

O [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] o ambiente de desenvolvimento integrado (IDE) tem a interface do usuário (UI) para alterar o plug-in de controle de origem atual. Essa área de teste fornece os casos de teste para o processo de selecionar o plug-in a ser usado para controle de código-fonte da solução.  
  
## <a name="command-menu-access"></a>Acesso ao Menu de comando  
 O seguinte [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] caminhos de menu de ambiente de desenvolvimento integrado são usados nos casos de teste.  
  
-   Controle de origem atual plug-in: **ferramentas** -> **opções** -> **controle do código-fonte** -> **seleção de plug-in** .  
  
-   Alterar fonte de ligação de controle: **arquivo** -> **controle de origem** -> **alterar controle do código-fonte**...  
  
## <a name="common-expected-behavior"></a>Comportamento esperado comuns  
 É possível alterar o plug-in para uma solução de controle de origem sem sair do Visual Studio ou recarregar a solução. Além disso, o plug-in de controle de origem atual é alterado automaticamente àquele usado por uma solução quando essa solução é carregada.  
  
## <a name="test-cases"></a>Casos de teste  
 Estes são os casos de teste específicos para a área de teste de comutação plug-in.  
  
### <a name="case-8a-automatic-change"></a>Caso 8a: automático de alterações  
  
#### <a name="expected-behavior"></a>Comportamento esperado  
 Quando um usuário carrega uma solução sob controle do código-fonte, a solução é carregada automaticamente e o plug-in de controle de origem apropriada é selecionada como atual.  
  
|Ação|Etapas de teste|Resultados esperados para verificar|  
|------------|----------------|--------------------------------|  
|Alteração de plug-in de controle de fonte automática|1.  Selecione plug-in em testar como atual (**ferramentas** -> **opções** -> **controle do código-fonte** -> **plug-in Seleção**.)<br />2.  Crie um novo projeto.<br />3.  Adicione a solução ao controle de origem.<br />4.  Selecione outro plug-in (por exemplo, [!INCLUDE[vsvss](../../includes/vsvss-md.md)]).<br />5.  Aceite solicitação de solução de descarregamento.<br />6.  Reabra a solução do disco.|Solução for aberta.<br /><br /> Plug-in em teste é o plug-in de controle de origem atual.|  
  
### <a name="case-8b-solution-based-change"></a>Caso 8b: alteração com base em solução  
  
#### <a name="expected-behavior"></a>Comportamento esperado  
 A solução pode ter seu plug-in de controle de origem associado alterado.  
  
|Ação|Etapas de teste|Resultados esperados para verificar|  
|------------|----------------|--------------------------------|  
|Alteração de plug-in para uma solução|1.  Selecione plug-in em testar como atual (**ferramentas** -> **opções** -> **controle do código-fonte** -> **plug-in Seleção**).<br />2.  Crie um novo projeto e solução.<br />3.  Adicione a solução ao controle de origem.<br />4.  Desassociar a solução de controle de origem (usando o **alterar controle do código-fonte** caixa de diálogo).<br />5.  Selecione outro plug-in (por exemplo, [!INCLUDE[vsvss](../../includes/vsvss-md.md)]).<br />6.  Recarregue a solução de disco se descarregado.<br />7.  Adicione a solução ao controle de origem.<br />8.  Desassociar a solução de controle de origem (usando **alterar controle do código-fonte** caixa de diálogo).<br />9. Selecione plug-in em teste novamente.<br />10. Recarregue a solução de disco se descarregado.<br />11. Associar a solução no local original (usando o **alterar controle do código-fonte** caixa de diálogo).|Solução é adicionada ao controle do código-fonte usando selecionado plug-in.|  
  
## <a name="see-also"></a>Consulte também  
 [Guia de teste para plug-ins de controle do código-fonte](../../extensibility/internals/test-guide-for-source-control-plug-ins.md)

