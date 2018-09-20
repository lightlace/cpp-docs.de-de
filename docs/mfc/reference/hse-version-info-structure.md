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
ms.openlocfilehash: 08b16c59f155864a781feccbfd08842380cccd01
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46433802"
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

