---
title: DEVNAMES-Struktur | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- DEVNAMES
dev_langs:
- C++
helpviewer_keywords:
- DEVNAMES
ms.assetid: aac97f60-2169-471a-ba5d-c0baed9eed9a
caps.latest.revision: 11
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 698a338c94dfa402dd51fa4f683b92a5d30cc0cd
ms.lasthandoff: 02/24/2017

---
# <a name="devnames-structure"></a>DEVNAMES-Struktur
Die `DEVNAMES` Struktur enthält Zeichenfolgen, die der Treiber, Geräte und Ausgabe-Anschlussnamen für einen Drucker zu identifizieren.  
  
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
 *wDriverOffset*  
 (Eingabe/Ausgabe) Gibt den Offset in Zeichen, die eine auf Null endende Zeichenfolge, die den Dateinamen (ohne Erweiterung) des Gerätetreibers enthält. Bei der Eingabe wird diese Zeichenfolge bestimmt den Drucker mit der ursprünglich im Dialogfeld angezeigt.  
  
 *wDeviceOffset*  
 (Eingabe/Ausgabe) Gibt den Offset in Zeichen, die Null-terminierte Zeichenfolge (maximal 32 Bytes, die das Nullzeichen) mit dem Namen des Geräts. Diese Zeichenfolge muss identisch mit der **DmDeviceName** Mitglied der [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) Struktur.  
  
 *wOutputOffset*  
 (Eingabe/Ausgabe) Gibt den Offset in Zeichen, die auf Null endende Zeichenfolge, die der DOS-Gerätename für das physikalische Ausgabemedium (Ausgabeanschluss) enthält.  
  
 *wDefault*  
 Gibt an, ob sich die Zeichenfolgen in der `DEVNAMES` -Struktur als Standarddrucker zu ermitteln. Diese Zeichenfolge wird verwendet, um sicherzustellen, dass seit der letzten Druckvorgang nicht als Standarddrucker geändert hat. Auf Benutzereingaben, wenn die **DN_DEFAULTPRN** Flag festgelegt ist, die anderen Werte der `DEVNAMES` Struktur mit den Standarddrucker verglichen. Wenn eine der Zeichenfolgen nicht übereinstimmen, wird eine Warnung angezeigt, die das Dokument neu formatiert werden angezeigt. Bei der Ausgabe der **wDefault** Element geändert wird, nur, wenn das Dialogfeld Seite einrichten angezeigt wurde und der Benutzer die Schaltfläche "OK hat". Die **DN_DEFAULTPRN** Flag wird festgelegt, wenn der Standarddrucker ausgewählt wurde. Wenn ein bestimmter Drucker ausgewählt ist, wird das Flag nicht festgelegt. Alle anderen Bits in diesem Member sind von der Prozedur Drucken-Dialogfeld für die interne Verwendung reserviert.  
  
## <a name="remarks"></a>Hinweise  
 Die **PrintDlg** Funktion verwendet diese Zeichenfolgen in das Dialogfeld Drucken vom System definierte Member initialisiert. Wenn der Benutzer das Dialogfeld geschlossen wird, werden Informationen über den ausgewählten Drucker in dieser Struktur zurückgegeben.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** commdlg.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CPrintDialog::CreatePrinterDC](../../mfc/reference/cprintdialog-class.md#createprinterdc)



