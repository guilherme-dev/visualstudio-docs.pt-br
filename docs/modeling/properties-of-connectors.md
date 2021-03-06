---
title: Propriedades de conectores
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- Domain-Specific Language, connectors
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: 5f7896c2e65f5ff01307e50cdc03483f6843fa67
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49881807"
---
# <a name="properties-of-connectors"></a>Propriedades de conectores
Os conectores representam as relações de domínio em um designer gerado.

 Para obter mais informações, consulte [como definir uma linguagem específica do domínio](../modeling/how-to-define-a-domain-specific-language.md). Para obter mais informações sobre como usar essas propriedades, consulte [personalizando e estendendo uma linguagem específica do domínio](../modeling/customizing-and-extending-a-domain-specific-language.md).

 Conectores têm as propriedades que são listadas na tabela a seguir.

|Propriedade|Descrição|Padrão|
|-|-|-|
|Cor|A cor deste conector.|Preto|
|Estilo de traço|O estilo de traço para a linha deste conector (sólido, traço, Dot, Traçoponto, Traçopontoponto ou personalizado).|Sólido|
|Estilo da extremidade de origem|O estilo da extremidade de origem para esse conector (HollowArrow, EmptyArrow, FilledArrow, EmptyDiamond, FilledDiamond ou nenhum).|Nenhum|
|Estilo da extremidade de destino|O estilo da extremidade de destino para esse conector (HollowArrow, EmptyArrow, FilledArrow, EmptyDiamond, FilledDiamond ou nenhum).|Nenhum|
|Cor do texto|A cor que é usada para os decoradores de texto que estão associados esse conector.|Preto|
|Espessura|A espessura da linha para esse conector, em polegadas.|0.03125|
|Modificador de acesso|O nível de acesso da classe (`public` ou `internal`).|Público|
|Atributos personalizados|Usado para adicionar atributos à classe de código de origem que é gerado a partir deste conector.|\<Nenhum >|
|Gera dupla derivado|Se `True`, serão geradas uma classe base e uma classe parcial (para dar suporte à personalização por meio de substituições). Para obter mais informações, consulte [substituindo e estendendo as Classes geradas](../modeling/overriding-and-extending-the-generated-classes.md).|False|
|Tem um construtor personalizado|Se `True`, um construtor personalizado será fornecido no código-fonte. Para obter mais informações, consulte [substituindo e estendendo as Classes geradas](../modeling/overriding-and-extending-the-generated-classes.md).|False|
|Modificador de herança|Descreve o tipo de herança da classe de código fonte que é gerado a partir do conector (`none`, `abstract` ou `sealed`).|nenhum|
|Conector base|A classe base desse conector.|(nenhum)|
|Nome|O nome deste conector.|Nome atual|
|Namespace|O namespace associado com esse conector.|Namespace atual|
|Tipo de dica de ferramenta|Como a dica de ferramenta é definida (fixo, variável ou nenhum). Se fixo, em seguida, o valor da `Fixed Tooltip Text` propriedade é usada como a dica de ferramenta; se a variável, em seguida, a dica de ferramenta é definida no código personalizado.|\<Nenhum >|
|Observações|Observações informais associadas esse conector.|\<Nenhum >|
|Estilo de roteamento|O estilo que é usado para o conector de roteamento. Um `Rectilinear` conector torna ativa ângulo à direita conforme necessário; um `Straight` conector não faz.|Retilíneo|
|Cor exposto como propriedade<br /><br /> Estilo de traço expostos como propriedade<br /><br /> Espessura exposta como propriedade<br /><br /> Expõe a cor do texto|Se `True`, o usuário pode definir a propriedade indicada de uma forma. Para configurar isso, a definição de forma com o botão direito e clique em **adicionar exposto**.|False|
|Descrição|Usado para documentar o designer gerado.|\<Nenhum >|
|Nome de Exibição|O nome que será exibido no designer gerado para esse conector.|\<Nenhum >|
|Texto de dica de ferramenta fixa|O texto que é usado para uma dica de ferramenta fixa.|\<Nenhum >|
|Palavra-chave de ajuda|A palavra-chave que é usada para indexar a Ajuda de F1 para este elemento.|\<Nenhum >|

## <a name="see-also"></a>Consulte também

- [Glossário de ferramentas de linguagem específica do domínio](http://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)