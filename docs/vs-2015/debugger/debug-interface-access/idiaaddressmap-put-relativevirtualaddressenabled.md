---
title: 'Idiaaddressmap:: Put_relativevirtualaddressenabled | Microsoft Docs'
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
- C++
helpviewer_keywords:
- IDiaAddressMap::put_relativeVirtualAddressEnabled method
ms.assetid: 767c078e-8ad7-4940-9e00-cae7704aadee
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7afc6534fc44ce74623a77c4b401e0858fcd5bbf
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49898662"
---
# <a name="idiaaddressmapputrelativevirtualaddressenabled"></a>IDiaAddressMap::put_relativeVirtualAddressEnabled
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Permite ao cliente habilitar ou desabilitar o cálculo e o uso de endereços virtuais relativos (RVA).  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp#  
HRESULT put_relativeVirtualAddressEnabled (   
   BOOL NewVal  
);  
```  
  
#### <a name="parameters"></a>Parâmetros  
 NewVal  
 [in] Definido como `TRUE` para habilitar, ou `FALSE` para desabilitar.  
  
## <a name="return-value"></a>Valor de retorno  
 Se for bem-sucedido, retornará `S_OK`; caso contrário, retorna um código de erro.  
  
## <a name="remarks"></a>Comentários  
 Endereços de objetos de depuração descritos pelas interfaces do DIA e, em relação à base, de imagem do executável podem ser recuperados como endereços virtuais.  
  
 O uso de RVAs é habilitado quando segmentos inicialmente são carregados de um arquivo PDB. Para obter o estado atual do uso de RVAs, chame o [idiaaddressmap:: Get_relativevirtualaddressenabled](../../debugger/debug-interface-access/idiaaddressmap-get-relativevirtualaddressenabled.md) método.  
  
 O `put_relativeVirtualAddress` método deve ser chamado para habilitar RVAs após uma chamada bem-sucedida para o [idiaaddressmap:: Set_imageheaders](../../debugger/debug-interface-access/idiaaddressmap-set-imageheaders.md) método estabeleceu novos cabeçalhos de imagem.  
  
## <a name="see-also"></a>Consulte também  
 [IDiaAddressMap](../../debugger/debug-interface-access/idiaaddressmap.md)   
 [Idiaaddressmap:: Get_relativevirtualaddressenabled](../../debugger/debug-interface-access/idiaaddressmap-get-relativevirtualaddressenabled.md)   
 [IDiaAddressMap::set_imageHeaders](../../debugger/debug-interface-access/idiaaddressmap-set-imageheaders.md)



