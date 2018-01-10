---
title: DEVNAMES-Struktur | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: DEVNAMES
dev_langs: C++
helpviewer_keywords: DEVNAMES [MFC]
ms.assetid: aac97f60-2169-471a-ba5d-c0baed9eed9a
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a3627af10dfb6fd18c54f772d26c33123127613a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="devnames-structure"></a>DEVNAMES-Struktur
Die `DEVNAMES` Struktur enthält die Zeichenfolgen, die die Treiber, Geräte und Ausgabe-Anschlussnamen für einen Drucker zu identifizieren.  
  
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
 (Eingabe/Ausgabe) Gibt den Offset in Zeichen, die eine auf Null endende Zeichenfolge, die den Dateinamen (ohne Erweiterung) für den Gerätetreiber enthält. Bei der Eingabe wird diese Zeichenfolge verwendet, um zu bestimmen, den Drucker anfänglich im Dialogfeld angezeigt.  
  
 *wDeviceOffset*  
 (Eingabe/Ausgabe) Gibt den Offset in Zeichen, die Null-terminierte Zeichenfolge (maximal 32 Byte, einschließlich der Null) mit dem Namen des Geräts an. Diese Zeichenfolge muss identisch mit der **DmDeviceName** Mitglied der [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) Struktur.  
  
 *wOutputOffset*  
 (Eingabe/Ausgabe) Gibt den Offset in Zeichen, die auf Null endende Zeichenfolge, die der DOS-Gerätename für das physikalische Ausgabemedium (Ausgabeport) enthält.  
  
 *wDefault*  
 Gibt an, ob die Zeichenfolgen in enthalten die `DEVNAMES` Struktur als Standarddrucker zu identifizieren. Diese Zeichenfolge wird verwendet, um sicherzustellen, dass seit der letzten Druckvorgang nicht als Standarddrucker geändert hat. Auf Eingabe-, If der **DN_DEFAULTPRN** Flag festgelegt ist, die anderen Werte der `DEVNAMES` Struktur anhand der aktuellen Standarddrucker überprüft. Wenn eine der Zeichenfolgen nicht übereinstimmen, wird eine Warnmeldung angezeigt informiert den Benutzer, den das Dokument neu formatiert werden muss. Bei der Ausgabe der **wDefault** Element geändert wird, nur, wenn das Dialogfeld Drucken Setup angezeigt wurde und der Benutzer die Schaltfläche "OK hat". Die **DN_DEFAULTPRN** Flag wird festgelegt, wenn als Standarddrucker ausgewählt wurde. Wenn Sie ein bestimmter Drucker ausgewählt ist, wird das Flag nicht festgelegt. Alle anderen Bits in diesem Element sind durch die Print-Standarddialogfelder für die interne Verwendung reserviert.  
  
## <a name="remarks"></a>Hinweise  
 Die **PrintDlg** Funktion verwendet diese Zeichenfolgen zum Initialisieren von Membern im System definierte Drucken-Dialogfeld. Wenn der Benutzer das Dialogfeld wird geschlossen, werden Informationen über den ausgewählten Drucker in dieser Struktur zurückgegeben.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** commdlg.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CPrintDialog::CreatePrinterDC](../../mfc/reference/cprintdialog-class.md#createprinterdc)


