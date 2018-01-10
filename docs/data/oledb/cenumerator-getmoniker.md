---
title: 'CEnumerator:: GetMoniker | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- GetMoniker
- CEnumerator.GetMoniker
- CEnumerator::GetMoniker
- ATL.CEnumerator.GetMoniker
- ATL::CEnumerator::GetMoniker
dev_langs: C++
helpviewer_keywords: GetMoniker method
ms.assetid: 69a5cf2d-4a94-41dc-812d-bc1661d516d2
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 41be8a27635d485ac4e2748df05211db7ff1c283
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cenumeratorgetmoniker"></a>CEnumerator::GetMoniker
Analysiert den Anzeigenamen die Komponente der Zeichenfolge zu extrahieren, die in ein Moniker konvertiert werden kann.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      HRESULT GetMoniker(   
   LPMONIKER* ppMoniker    
) const throw( );  
HRESULT GetMoniker(   
   LPMONIKER* ppMoniker,   
   LPCTSTR lpszDisplayName    
) const throw( );  
```  
  
#### <a name="parameters"></a>Parameter  
 *ppMoniker*  
 [out] Der Moniker des Anzeigenamens analysiert ([cenumeratoraccessor:: M_szparsename](../../data/oledb/cenumeratoraccessor-m-szparsename.md)) der aktuellen Zeile.  
  
 *lpszDisplayName*  
 [in] Der Anzeigename, zu analysieren.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT`-Objekt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CEnumerator-Klasse](../../data/oledb/cenumerator-class.md)