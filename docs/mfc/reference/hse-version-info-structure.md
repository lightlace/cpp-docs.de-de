---
title: HSE_VERSION_INFO-Struktur | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: HSE_VERSION_INFO
dev_langs: C++
helpviewer_keywords: HSE_VERSION_INFO structure [MFC]
ms.assetid: 4837312d-68c8-4d05-9afa-1934d7d49b20
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 78b1ed79093db179e00f262b61934ff9c293ff18
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="hseversioninfo-structure"></a>HSE_VERSION_INFO-Struktur
Diese Struktur verweist die `pVer` Parameter in der `CHttpServer::GetExtensionVersion` Memberfunktion. Er bietet eine ISA-Versionsnummer und eine textbeschreibung der ISA  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef struct _HSE_VERSION_INFO {  
    DWORD dwExtensionVersion;  
    CHAR lpszExtensionDesc[HSE_MAX_EXT_DLL_NAME_LEN];  
} HSE_VERSION_INFO, *LPHSE_VERSION_INFO;  
```  
  
#### <a name="parameters"></a>Parameter  
 *dwExtensionVersion*  
 Die Versionsnummer der ISA  
  
 *lpszExtensionDesc*  
 Die textbeschreibung der ISA Die standardmäßige Implementierung bietet Platzhaltertext; Überschreiben Sie `CHttpServer::GetExtensionVersion` um eine eigene Beschreibung bereitzustellen.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** httpext.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)

