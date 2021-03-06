---
title: 'Como: depurar usando a depuração RPC de servidores e clientes COM | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.com
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- RPC (Remote Procedure Call), debugging COM clients and servers
- COM, debugging
- RPC (Remote Procedure Call)
- RPC (Remote Procedure Call), debugging
- COM clients, debugging
- COM servers, debugging
- out-of-process remote procedure call debugging
- remote debugging, RPC (Remote Procedure Call)
- in-process remote procedure call debugging
ms.assetid: 3e8526c8-43b5-4b87-8e0d-b22c24f0a3ea
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1404d81502aaa0579c20511f3eecafa86607df0d
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/18/2018
ms.locfileid: "31473732"
---
# <a name="how-to-debug-com-clients-and-servers-using-rpc-debugging"></a>Como depurar clientes e servidores COM usando a depuração RPC
Você pode usar a depuração de chamada de procedimento remoto (RPC) para depurar aplicativos cliente/servidor COM. Você deve habilitar a depuração de RPC para usá-lo. Com a depuração de RPC habilitada, quando você entrar na chamada do servidor do cliente, o depurador anexará ao servidor e permitirá depurar o código. Quando o depurador for anexado, você poderá usar todos os recursos do depurador com o cliente e os processos do servidor.  
  
### <a name="to-enable-rpc-debugging"></a>Para habilitar a depuração de RPC  
  
1.  No menu **Ferramentas**, clique em **Opções**.  
  
2.  No **opções** caixa de diálogo, clique o **depuração** pasta.  
  
3.  Clique o **nativo** página.  
  
4.  Selecione o **depuração RPC** caixa de seleção.  
  
    > [!NOTE]
    >  Para depurar chamadas de RPC, você deve ter privilégios de Administrador ou Usuário avançado.  
  
    > [!NOTE]
    >  A entrada de RPC em um servidor remoto que executa o Microsoft Windows Vista só funcionará se um depurador nativo for anexado ao servidor remoto. Caso contrário, a chamada de RPC apresentará falha sem uma mensagem de erro. De outro modo, a chamada de RPC será concluída, mas a depuração da chamada de RPC não funcionará.  
  
## <a name="see-also"></a>Consulte também  
 [Depuração de servidor COM e contêiner](../debugger/com-server-and-container-debugging.md)  
 [Depuração no Visual Studio](../debugger/index.md) [tour pelos recursos do depurador](../debugger/debugger-feature-tour.md)