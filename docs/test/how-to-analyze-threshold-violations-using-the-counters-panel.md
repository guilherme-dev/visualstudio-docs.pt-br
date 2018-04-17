---
title: Violações de limite para testes de carga no Visual Studio | Microsoft Docs
ms.date: 10/19/2016
ms.topic: article
helpviewer_keywords:
- load tests, threshold violations
ms.assetid: 0126d7b7-0538-4ea9-9046-6556654b3b9d
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-test
ms.openlocfilehash: 9c511bb3edf8ad8277b367733f85108d9587898e
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2018
---
# <a name="how-to-analyze-threshold-violations-using-the-counters-panel-in-load-test-analyzer"></a>Como analisar violações de limite usando o painel Contadores no Analisador de Teste de Carga

O painel Contadores permanece visível na exibição Gráficos e na exibição Tabelas do Analisador de Testes de Carga enquanto um teste de carga está em execução ou quando você está analisando o resultado de um teste de carga. Consulte [Analisar resultados de teste de carga na exibição de gráficos](../test/analyze-load-test-results-in-the-graphs-view.md), [Analisar erros e resultados de teste de carga na exibição de tabelas](../test/analyze-load-test-results-and-errors-in-the-tables-view.md) e [Como acessar resultados de teste de carga para análise](../test/how-to-access-load-test-results-for-analysis.md).

 As violações de limite são associadas a contadores de desempenho específicos e indicam que o contador de desempenho excedeu ou ficou abaixo de um valor de limite definido. Os ícones no painel de contadores informam as violações de limite.

 ![Nó de computador do painel de contador](../test/media/ltest_compnode.png "LTest_CompNode")

 O ícone de uma violação de limite é propagado do nó da árvore em que reside o contador com falha até a raiz. O ícone alerta o usuário para uma violação em um contador que talvez não esteja visível na árvore porque a árvore não foi expandida. Um exemplo do ícone pode ser visto no **Nó Computadores** do painel Contadores na ilustração anterior.

 O ícone será um dos seguintes:

 ![Nenhuma violação de limite](../test/media/icon_ltest_1.gif "Icon_LTest_1") Nenhuma violação de limite.

 ![Uma violação de limite crítica no último intervalo](../test/media/icon_ltest_2.gif "Icon_LTest_2") Uma violação de limite crítica no último intervalo.

 ![Uma violação de limite crítica em um intervalo anterior](../test/media/icon_ltest_3.gif "Icon_LTest_3") Uma violação de limite crítica em um intervalo anterior.

 ![Uma violação de limite com aviso no último intervalo](../test/media/icon_ltest_4.gif "Icon_LTest_4") Uma violação de limite com aviso no último intervalo.

 ![Uma violação de limite com aviso em um intervalo anterior](../test/media/icon_ltest_5.gif "Icon_LTest_5") Uma violação de limite com aviso em um intervalo anterior.

## <a name="to-analyze-threshold-violations-in-the-counters-panel"></a>Para analisar violações de limite no painel Contadores

1.  Depois que um teste de carga terminar ou depois que você carregar um resultado do teste, na barra de ferramentas do Analisador de Teste de Carga, escolha **Gráficos** ou **Tabelas**.

     O painel Contadores é mostrado na exibição Gráficos ou na exibição Tabelas.

2.  Se o painel Contadores não estiver visível, escolha **Mostrar painel de contadores** na barra de ferramentas.

     Todos os nós que contenham violações de limite incluirão um dos ícones listados acima.

3.  Expanda o nó que contém um ícone de limite, como o nó **Computadores**, conforme mostrado na ilustração anterior intitulada "Nó Computadores no painel Contadores com violação de limite". Continue expandindo o nó até chegar ao contador de desempenho com a violação de limite. Por exemplo, a ilustração mostra a instância com falha do **Adaptador de rede de barramento com falha do Microsoft Virtual Machine**.

4.  (Opcional) Clique com o botão direito do mouse no contador de desempenho com a violação de limite e selecione uma das seguintes opções:

    -   **Mostrar Contador no Gráfico**: na exibição Gráficos, o contador de desempenho é adicionado e realçado no gráfico selecionado. Para obter mais informações, consulte [Como adicionar e excluir contadores em gráficos](../test/how-to-add-and-delete-counters-on-graphs-in-load-test-results.md).

        > [!NOTE]
        > Os ícones de violação de limite também podem ser mostrados no gráfico na exibição Gráficos. O ícone de limite é exibido no gráfico ao lado do ponto de dados onde a violação de limite ocorreu. Para fazer isso, escolha a lista suspensa **Mostrar legenda** na barra de ferramentas e selecione **Mostrar violações de limite no gráfico**.

    -   **Mostrar Contador na Legenda**: na legenda, o contador de desempenho é adicionado e selecionado. Para obter mais informações, consulte [Usando a legenda de exibição dos gráficos para analisar testes de carga](../test/use-the-graphs-view-legend-to-analyze-load-tests.md).

    -   **Adicionar Gráfico**:

    1.  A caixa de diálogo **Digite o nome do gráfico** é exibida.

    2.  Na caixa de texto **Nome do gráfico**, digite um nome para o novo gráfico e escolha **OK**.

    3.  (Opcional) Clique com o botão direito do mouse no contador de desempenho novamente e selecione **Mostrar Contador no Gráfico**.

         Para obter mais informações, consulte [Como criar gráficos personalizados](../test/how-to-create-custom-graphs-in-load-test-results.md).

5.  (Opcional) Se você estiver analisando a violação de limite em um resultado de teste de carga concluído, considere usar os recursos de zoom na exibição Gráficos. Para obter mais informações, consulte [Como ampliar uma região do gráfico](../test/how-to-zoom-in-on-a-region-of-the-graph-in-load-test-results.md).

    > [!TIP]
    > Se qualquer violação de limite for detectada durante a execução do teste de carga, um link intitulado "violações de limite", incluindo o número de violações, estará presente na barra de status do Analisador de Testes de Carga. É possível escolher o link para exibir todas as violações de limite na tabela **Limites** da exibição Tabelas.

## <a name="see-also"></a>Consulte também

- [Usando o painel Contadores nas exibições de Gráficos e Tabelas](../test/counters-panel-in-load-test-analyzer.md)
- [Analisar resultados de teste de carga](../test/analyze-load-test-results-using-the-load-test-analyzer.md)