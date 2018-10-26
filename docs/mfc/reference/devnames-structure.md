---
title: DEVNAMES-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- DEVNAMES
dev_langs:
- C++
helpviewer_keywords:
- DEVNAMES [MFC]
ms.assetid: aac97f60-2169-471a-ba5d-c0baed9eed9a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d91a44a38d331a49927d5129c5002eef53c224ad
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50077971"
---
# <a name="devnames-structure"></a>DEVNAMES-Struktur

Die `DEVNAMES` Struktur enthält Zeichenfolgen, die die Treiber, Gerät und die Namen der Ausgabe-Anschlüsse für einen Drucker zu identifizieren.

## <a name="syntax"></a>Syntax

```
typedef struct tagDEVNAMES { /* dvnm */
    WORD wDriverOffset;
    WORD wDeviceOffset;
    WORD wOutputOffset;
    WORD wDefault; */* driver,
    device,
    and port-name strings follow wDefault */
} DEVNAMES;
```

#### <a name="parameters"></a>Parameter

*wDriverOffset*<br/>
(Eingabe/Ausgabe) Gibt den Offset in Zeichen, um eine auf Null endende Zeichenfolge, die den Dateinamen (ohne Erweiterung) für den Gerätetreiber enthält. Bei der Eingabe wird diese Zeichenfolge verwendet, um zu bestimmen, den Drucker mit der ursprünglich im Dialogfeld angezeigt.

*wDeviceOffset*<br/>
(Eingabe/Ausgabe) Gibt den Offset in Zeichen, die Null-terminierte Zeichenfolge (maximal 32 Bytes, einschließlich Null), die den Namen des Geräts enthält. Diese Zeichenfolge muss identisch mit der `dmDeviceName` Mitglied der [DEVMODE](/windows/desktop/api/wingdi/ns-wingdi-_devicemodea) Struktur.

*wOutputOffset*<br/>
(Eingabe/Ausgabe) Gibt den Offset in Zeichen, die Null-terminierte Zeichenfolge, die den DOS-Gerätenamen für das physische Ausgabemedium (Ausgabe-Anschluss) enthält.

*wDefault*<br/>
Gibt an, ob die Zeichenfolgen in enthalten die `DEVNAMES` Struktur identifizieren den Standarddrucker. Diese Zeichenfolge wird verwendet, um sicherzustellen, dass es sich bei der Standarddrucker seit der letzten Druckvorgang nicht geändert hat. Bei der Eingabe, wenn die DN_DEFAULTPRN-Flag festgelegt ist, die andere Werte der `DEVNAMES` Struktur werden mit den aktuellen Standarddrucker verglichen. Wenn einer der Zeichenfolgen nicht übereinstimmen, wird eine Warnmeldung angezeigt, den Benutzer, den das Dokument möglicherweise umformatiert werden darüber informiert. Bei der Ausgabe der `wDefault` Element geändert wird, nur, wenn das Dialogfeld Drucken-Setup angezeigt wurde und der Benutzer die Schaltfläche "OK hat". Die DN_DEFAULTPRN-Flag wird festgelegt, wenn der Standarddrucker ausgewählt wurde. Wenn Sie ein bestimmten Drucker aktiviert ist, wird das Flag nicht festgelegt. Alle anderen Bits in diesem Member sind von der Print-Dialogfeldprozedur für die interne Verwendung reserviert.

## <a name="remarks"></a>Hinweise

Die `PrintDlg` Funktion verwendet diese Zeichenfolgen zum Initialisieren von Membern im System definierte Dialogfeld Drucken. Wenn der Benutzer das Dialogfeld schließt, werden Informationen über den ausgewählten Drucker in dieser Struktur zurückgegeben.

## <a name="requirements"></a>Anforderungen

**Header:** commdlg.h

## <a name="see-also"></a>Siehe auch

[Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CPrintDialog::CreatePrinterDC](../../mfc/reference/cprintdialog-class.md#createprinterdc)

