---
title: DHtmlUrlEventMapEntry-Struktur
ms.date: 11/04/2016
f1_keywords:
- DHtmlUrlEventMapEntry
helpviewer_keywords:
- DHtmlUrlEventMapEntry structure [MFC]
ms.assetid: 43117c1f-1a51-406c-aa2f-fea647080049
ms.openlocfilehash: 0a1dc86080c094a7ac89940cd43a8edac973e10c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50431628"
---
# <a name="dhtmlurleventmapentry-structure"></a>DHtmlUrlEventMapEntry-Struktur

Die `DHtmlUrlEventMapEntry` Struktur stellt mehrere URL-Ereignis der Unterstützung von Karten bereit.

## <a name="syntax"></a>Syntax

```
struct DHtmlUrlEventMapEntry
{
LPCTSTR szUrl;
const DHtmlEventMapEntry *pEventMap;
};
```

#### <a name="parameters"></a>Parameter

*szUrl*<br/>
Die URL.

*pEventMap*<br/>
Die ereigniszuordnung mit der URL verknüpft ist.

## <a name="requirements"></a>Anforderungen

**Header:** afxdhtml.h

## <a name="see-also"></a>Siehe auch

[Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)

