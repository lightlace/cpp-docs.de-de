---
title: PAINTSTRUCT-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- PAINTSTRUCT
dev_langs:
- C++
helpviewer_keywords:
- PAINTSTRUCT structure [MFC]
ms.assetid: 81ce4993-3e89-43b2-8c98-7946f1314d24
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 531dbc3c0e9b609aeaf5d9179491aa0fb3990363
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46382920"
---
# <a name="paintstruct-structure"></a>PAINTSTRUCT-Struktur

Die `PAINTSTRUCT` Struktur enthält Informationen, die verwendet werden kann, um den Clientbereich eines Fensters zu zeichnen.

## <a name="syntax"></a>Syntax

```
typedef struct tagPAINTSTRUCT {
    HDC hdc;
    BOOL fErase;
    RECT rcPaint;
    BOOL fRestore;
    BOOL fIncUpdate;
    BYTE rgbReserved[16];
} PAINTSTRUCT;
```

#### <a name="parameters"></a>Parameter

*hdc*<br/>
Identifiziert den Anzeigekontext, die zum Zeichnen verwendet werden.

*fErase*<br/>
Gibt an, ob der Hintergrund neu gezeichnet werden muss. Es ist nicht 0, wenn die Anwendung neu Hintergrund gezeichnet werden soll. Die Anwendung ist verantwortlich für den Hintergrund zeichnen, wenn eine Windows-Fensterklasse ohne ein Hintergrundpinsel erstellt wird (finden Sie in der Beschreibung der `hbrBackground` Mitglied der [WNDCLASS](https://msdn.microsoft.com/library/windows/desktop/ms633576) Struktur im Windows SDK).

*rcPaint*<br/>
Gibt an, der oberen linken und unteren linken Ecke des Rechtecks in dem das Zeichnen angefordert wird.

*fRestore*<br/>
Reservierten Member. Sie wird intern von Windows verwendet.

*fIncUpdate*<br/>
Reservierten Member. Sie wird intern von Windows verwendet.

*RgbReserved [16]*<br/>
Reservierten Member. Eine reservierte Speicherblock intern von Windows verwendet.

## <a name="requirements"></a>Anforderungen

**Header:** winuser.h

## <a name="see-also"></a>Siehe auch

[Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CPaintDC::m_ps](../../mfc/reference/cpaintdc-class.md#m_ps)

