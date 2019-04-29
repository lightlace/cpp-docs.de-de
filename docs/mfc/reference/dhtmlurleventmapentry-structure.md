---
title: DHtmlUrlEventMapEntry-Struktur
ms.date: 11/04/2016
f1_keywords:
- DHtmlUrlEventMapEntry
helpviewer_keywords:
- DHtmlUrlEventMapEntry structure [MFC]
ms.assetid: 43117c1f-1a51-406c-aa2f-fea647080049
ms.openlocfilehash: c9b58067a9c8b6a71cd22b654a2f82ba0f8bfe36
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62322734"
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
