---
title: PAINTSTRUCT-Struktur
ms.date: 11/04/2016
f1_keywords:
- PAINTSTRUCT
helpviewer_keywords:
- PAINTSTRUCT structure [MFC]
ms.assetid: 81ce4993-3e89-43b2-8c98-7946f1314d24
ms.openlocfilehash: f1b901ef26c61adbedb3bbe56808cd94bdfad30d
ms.sourcegitcommit: b032daf81cb5fdb1f5a988277ee30201441c4945
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2018
ms.locfileid: "51694646"
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
Gibt an, ob der Hintergrund neu gezeichnet werden muss. Es ist nicht 0, wenn die Anwendung neu Hintergrund gezeichnet werden soll. Die Anwendung ist verantwortlich für den Hintergrund zeichnen, wenn eine Windows-Fensterklasse ohne ein Hintergrundpinsel erstellt wird (finden Sie in der Beschreibung der `hbrBackground` Mitglied der [WNDCLASS](/windows/desktop/api/winuser/ns-winuser-tagwndclassa) Struktur im Windows SDK).

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

