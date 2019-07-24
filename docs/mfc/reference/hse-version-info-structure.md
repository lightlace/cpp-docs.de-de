---
title: HSE_VERSION_INFO-Struktur
ms.date: 11/04/2016
f1_keywords:
- HSE_VERSION_INFO
helpviewer_keywords:
- HSE_VERSION_INFO structure [MFC]
ms.assetid: 4837312d-68c8-4d05-9afa-1934d7d49b20
ms.openlocfilehash: 97f34bebae8a486a825d04b23c5a92fbd4aefa42
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62322109"
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

*dwExtensionVersion*<br/>
Die Versionsnummer der Anweisungssequenz

*lpszExtensionDesc*<br/>
Die textbeschreibung des der Anweisungssequenz Die Standardimplementierung stellt Platzhaltertext bereit; außer Kraft setzen `CHttpServer::GetExtensionVersion` eigene Beschreibung angeben.

## <a name="requirements"></a>Anforderungen

**Header:** httpext.h

## <a name="see-also"></a>Siehe auch

[Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)
