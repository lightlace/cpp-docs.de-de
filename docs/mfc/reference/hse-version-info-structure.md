---
title: HSE_VERSION_INFO-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- HSE_VERSION_INFO
dev_langs:
- C++
helpviewer_keywords:
- HSE_VERSION_INFO structure [MFC]
ms.assetid: 4837312d-68c8-4d05-9afa-1934d7d49b20
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: daf1565c2fe2d7a4620f83b765671fea80502102
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37335814"
---
# <a name="hseversioninfo-structure"></a>HSE_VERSION_INFO-Struktur
Diese Struktur verweist die *pVer* Parameter in der `CHttpServer::GetExtensionVersion` Member-Funktion. Es bietet der ISA-Versionsnummer und eine textbeschreibung der Anweisungssequenz  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef struct _HSE_VERSION_INFO {  
    DWORD dwExtensionVersion;  
    CHAR lpszExtensionDesc[HSE_MAX_EXT_DLL_NAME_LEN];  
} HSE_VERSION_INFO, *LPHSE_VERSION_INFO;  
```  
  
#### <a name="parameters"></a>Parameter  
 *dwExtensionVersion*  
 Die Versionsnummer der Anweisungssequenz  
  
 *lpszExtensionDesc*  
 Die textbeschreibung des der Anweisungssequenz Die Standardimplementierung stellt Platzhaltertext bereit; außer Kraft setzen `CHttpServer::GetExtensionVersion` eigene Beschreibung angeben.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** httpext.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)

