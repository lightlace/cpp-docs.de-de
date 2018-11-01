---
title: COMPAREITEMSTRUCT-Struktur
ms.date: 11/04/2016
f1_keywords:
- COMPAREITEMSTRUCT
helpviewer_keywords:
- COMPAREITEMSTRUCT structure [MFC]
ms.assetid: 4b7131a5-5c7d-4e98-aac7-e85650262b52
ms.openlocfilehash: 78a6e76ee3bbac5b32eb4bccf45578e63f763b75
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50465415"
---
# <a name="compareitemstruct-structure"></a>COMPAREITEMSTRUCT-Struktur

Die `COMPAREITEMSTRUCT` Struktur bereitstellt, die Bezeichner und der Anwendung bereitgestellte Daten für zwei Elemente in einem sortierten, vom Besitzer gezeichnetes Listenfeld oder Kombinationsfeld.

## <a name="syntax"></a>Syntax

```
typedef struct tagCOMPAREITEMSTRUCT {
    UINT CtlType;
    UINT CtlID;
    HWND hwndItem;
    UINT itemID1;
    DWORD itemData1;
    UINT itemID2;
    DWORD itemData2;
} COMPAREITEMSTRUCT;
```

#### <a name="parameters"></a>Parameter

*CtlType*<br/>
Odt_combobox (womit eine Ownerdrawn-Listenfeld angegeben wird) oder ODT_COMBOBOX (die ein Ownerdrawn-Kombinationsfeld angibt).

*CtlID*<br/>
Die Steuerelement-ID für das Listenfeld oder Kombinationsfeld.

*hwndItem*<br/>
Das Fensterhandle des Steuerelements.

*itemID1*<br/>
Der Index des ersten Elements in das Listenfeld oder Kombinationsfeld, die mit dem verglichen wird.

*itemData1*<br/>
Von der Anwendung bereitgestellten Daten für das erste Element mit dem verglichen wird. Dieser Wert wurde im Aufruf übergeben, die das Element im Kombinationsfeld oder Liste hinzugefügt.

*itemID2*<br/>
Der Index des zweiten Elements in das Listenfeld oder Kombinationsfeld, die mit dem verglichen wird.

*itemData2*<br/>
Von der Anwendung bereitgestellten Daten für das zweite Element verglichen wird. Dieser Wert wurde im Aufruf übergeben, die das Element im Kombinationsfeld oder Liste hinzugefügt.

## <a name="remarks"></a>Hinweise

Wenn eine Anwendung ein neues Element mit einem Ownerdrawn-Listenfeld oder Kombinationsfeld erstellt, mit der Formatvorlage CBS_SORT oder LBS_SORT hinzufügt, sendet Windows eine WM_COMPAREITEM-Nachricht an dem Besitzer. Die *lParam* -Parameter der Nachricht enthält einen long-Zeiger auf eine `COMPAREITEMSTRUCT` Struktur. Bei Empfang der Nachricht an, der Besitzer vergleicht die beiden Elemente und gibt einen Wert, der angibt, welches Element vor den anderen sortiert zurück.

## <a name="requirements"></a>Anforderungen

**Header:** winuser.h

## <a name="see-also"></a>Siehe auch

[Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CWnd::OnCompareItem](../../mfc/reference/cwnd-class.md#oncompareitem)

