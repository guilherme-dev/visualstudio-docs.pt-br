---
title: Cache de dados | Microsoft Docs
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data caching [Office development in Visual Studio], about caching data
- data [Office development in Visual Studio], caching
- data caching [Office development in Visual Studio]
ms.assetid: 6f34251e-7d31-4f2b-ac17-42fd2837c626
caps.latest.revision: "36"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 0d5f044f1f1d0f36918939a67d9d2e5bb1899929
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/31/2017
---
# <a name="caching-data"></a>Armazenando dados em cache
  Você pode armazenar em cache objetos de dados em uma personalização no nível do documento para que os dados podem ser acessados offline ou sem abrir o Microsoft Office Word ou o Microsoft Office Excel. Para armazenar em cache um objeto, o objeto deve ter um tipo de dados que atenda a certos requisitos. Muitos tipos de dados comum do .NET Framework atendem a esses requisitos, incluindo <xref:System.String>, <xref:System.Data.DataSet>, e <xref:System.Data.DataTable>.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
 Há duas maneiras de adicionar um objeto para o cache de dados:  
  
-   Para adicionar um objeto para o cache de dados quando a solução é criada, aplicar o <xref:Microsoft.VisualStudio.Tools.Applications.Runtime.CachedAttribute> de atributo para a declaração do objeto. Para obter mais informações, consulte [como: dados de Cache para uso Offline ou em um servidor](../vsto/how-to-cache-data-for-use-offline-or-on-a-server.md).  
  
-   Para adicionar programaticamente um objeto para o cache de dados em tempo de execução, use o `StartCaching` método de um host de item, como o `ThisDocument` ou `ThisWorkbook` classes. Para obter mais informações, consulte [como: Cache programaticamente uma fonte de dados em um documento do Office](../vsto/how-to-programmatically-cache-a-data-source-in-an-office-document.md).  
  
 Depois de adicionar um objeto para o cache de dados, você pode acessar e modificar os dados em cache sem iniciar o Word ou Excel. Para obter mais informações, consulte [acessar dados em documentos no servidor](../vsto/accessing-data-in-documents-on-the-server.md).  
  
## <a name="requirements-for-data-objects-to-be-cached"></a>Requisitos para objetos de dados a ser armazenado em cache  
 Para armazenar em cache um objeto de dados em sua solução, o objeto deve atender a esses requisitos:  
  
-   Ser um campo de leitura/gravação público ou propriedade de um item de host, como o `ThisDocument` ou `ThisWorkbook` classes.  
  
-   Não se um indexador ou outra propriedade com parâmetros.  
  
 Além disso, o objeto de dados deve ser serializado pela <xref:System.Xml.Serialization.XmlSerializer> classe, o que significa que o tipo de objeto deve ter as seguintes características:  
  
-   Ser um tipo público.  
  
-   Ter um construtor público sem parâmetros.  
  
-   Não execute o código que requer privilégios de segurança adicional.  
  
-   Expor somente leitura/gravação propriedades públicas (outras propriedades serão ignoradas).  
  
-   Não expor matrizes multidimensionais (matrizes aninhadas são aceitos).  
  
-   Interfaces não retorno de propriedades e campos.  
  
-   Não implementa <xref:System.Collections.IDictionary> se uma coleção.  
  
 Quando você armazena em cache um objeto de dados, o [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] serializa o objeto em uma cadeia de caracteres XML que é armazenada em um *parte XML personalizada* no documento. Para obter mais informações, consulte [visão geral de partes de XML personalizado](../vsto/custom-xml-parts-overview.md).  
  
## <a name="cached-data-size-limits"></a>Limites de tamanho de dados armazenados em cache  
 Existem alguns limites para a quantidade total de dados que você pode adicionar o cache de dados em um documento e o tamanho de qualquer objeto individual no cache de dados. Se você exceder esses limites, o aplicativo pode fechar inesperadamente, quando os dados são salvos no cache de dados.  
  
 Para evitar esses limites, siga estas diretrizes:  
  
-   Não adicione qualquer objeto maior do que 10 MB para o cache de dados.  
  
-   Não adicione mais de 100 MB de dados total para o cache de dados em um único documento.  
  
 Estes são valores aproximados. Os limites exatos dependem de vários fatores, incluindo a RAM disponível e o número de processos em execução.  
  
## <a name="controlling-the-behavior-of-cached-objects"></a>Controlar o comportamento de objetos armazenados em cache  
 Para obter mais controle sobre o comportamento de um objeto armazenado em cache, você pode implementar o <xref:Microsoft.VisualStudio.Tools.Applications.Runtime.ICachedType> interface no tipo do objeto armazenado em cache. Por exemplo, você pode implementar essa interface, se você quiser controlar como o usuário é notificado quando o objeto foi alterado. Para obter exemplos de código que demonstram como implementar <xref:Microsoft.VisualStudio.Tools.Applications.Runtime.ICachedType>, consulte o `ControlCollection` classe no exemplo de controles dinâmicos do Excel e Word dinâmico controles de exemplo em [amostras de desenvolvimento do Office e explicações passo a passo](../vsto/office-development-samples-and-walkthroughs.md).  
  
## <a name="persisting-changes-to-cached-data-in-password-protected-documents"></a>Mantendo alterações aos dados armazenados em cache em documentos protegidos por senha  
 Se você armazenar em cache objetos de dados em um documento protegido com uma senha, as alterações nos dados armazenados em cache não serão salvas. Você pode salvar as alterações aos dados armazenados em cache, substituindo os dois métodos. Substituir esses métodos para remover temporariamente a proteção quando o documento é salvo e, em seguida, aplique novamente a proteção depois que a operação for concluída.  
  
 Para obter mais informações, consulte [como: Cache de dados em um documento protegida por senha](../vsto/how-to-cache-data-in-a-password-protected-document.md).  
  
## <a name="preventing-data-loss-when-adding-null-values-to-the-data-cache"></a>Prevenção de perda de dados durante a adição de valores nulos para o Cache de dados  
 Quando você adiciona objetos para o cache de dados, todos os objetos armazenados em cache devem ser inicializados para não**nulo** valor antes do documento é salvo e fechado. Se tiver qualquer objeto armazenado em cache um **nulo** valor quando o documento é salvo e fechado, o [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] removerá automaticamente todos os objetos em cache do cache de dados.  
  
 Se você adicionar um objeto com um **nulo** valor para o cache de dados usando o <xref:Microsoft.VisualStudio.Tools.Applications.Runtime.CachedAttribute> atributo em tempo de design, você pode usar o <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> classe ao inicializar os dados em cache objetos antes de abrir o documento. Isso é útil se você quiser inicializar os dados em cache em um servidor sem o Word ou Excel instalados, para que o documento está aberto por um usuário final. Para obter mais informações, consulte [acessar dados em documentos no servidor](../vsto/accessing-data-in-documents-on-the-server.md).  
  
## <a name="see-also"></a>Consulte também  
 [Como: dados armazenados em Cache para uso Offline ou em um servidor](../vsto/how-to-cache-data-for-use-offline-or-on-a-server.md)   
 [Como: Cache programaticamente uma fonte de dados em um documento do Office](../vsto/how-to-programmatically-cache-a-data-source-in-an-office-document.md)   
 [Como: armazenar em Cache dados em um documento protegido por senha](../vsto/how-to-cache-data-in-a-password-protected-document.md)   
 [Instruções passo a passo: criando uma relação mestre detalhada usando um conjunto de dados armazenado em cache](../vsto/walkthrough-creating-a-master-detail-relation-using-a-cached-dataset.md)  
  
  