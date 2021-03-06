---
title: Como posso saber se meus ponteiros corrompem um endereço de memória? | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
- C++
helpviewer_keywords:
- addresses, pointers corrupting memory address
- memory, corruption
- pointers, corrupting memory addresses
- memory address corruption by pointers
- debugging [C++], memory corruption
- corrupted memory address
ms.assetid: a147c939-4fb1-415c-8410-cf303781e9e8
caps.latest.revision: 22
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 04df8c5dfc0d6fbf57183cf90ab0fd8a4fc79686
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49217303"
---
# <a name="how-can-i-find-out-if-my-pointers-corrupt-a-memory-address"></a>Como posso saber se meus ponteiros corrompem um endereço de memória?
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Descrição do problema  
 Eu acho que um de meus ponteiros pode estar danificando a memória no endereço 0x00408000. Como posso descobrir o que está acontecendo lá?  
  
## <a name="solution"></a>Solução  
  
#### <a name="check-for-heap-corruption"></a>Verificação de danos do heap  
  
-   A maior parte das corrupções de memória acontece, na verdade, devido à corrupção da heap. Tente usar o utilitário global dos sinalizadores (gflags.exe) ou pageheap.exe. Ver [ http://support.microsoft.com/default.aspx?scid=kb; en-us; 286470](http://support.microsoft.com/default.aspx?scid=kb;en-us;286470).  
  
#### <a name="to-find-where-the-memory-address-is-modified"></a>Para localizar onde o endereço de memória foi alterado  
  
1.  Defina um ponto de interrupção de dados em 0x00408000. Ver [definir um ponto de interrupção de alteração de dados (somente C++ nativo)](../debugger/using-breakpoints.md#BKMK_set_a_data_breakpoint_native_cplusplus_only).  
  
2.  Quando você atinge o ponto de interrupção, use o **memória** de conteúdo da janela para exibir a memória que começam em 0x00408000. Para obter mais informações, consulte [memória Windows](../debugger/memory-windows.md).  
  
## <a name="see-also"></a>Consulte também  
 [Perguntas frequentes do código nativo de depuração](../debugger/debugging-native-code-faqs.md)   
 [Depurando código nativo](../debugger/debugging-native-code.md)



