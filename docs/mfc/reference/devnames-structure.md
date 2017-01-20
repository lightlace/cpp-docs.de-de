---
title: "DEVNAMES-Struktur"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "DEVNAMES"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DEVNAMES"
ms.assetid: aac97f60-2169-471a-ba5d-c0baed9eed9a
caps.latest.revision: 11
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# DEVNAMES-Struktur
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `DEVNAMES`\-Struktur enthält Zeichenfolgen, die den Treiber, das Gerät und die Ausgabeanschlussnamen für einen Drucker identifizieren.  
  
## Syntax  
  
```  
  
      typedef struct tagDEVNAMES { /* dvnm */  
    WORD wDriverOffset;  
    WORD wDeviceOffset;  
    WORD wOutputOffset;  
    WORD wDefault;  
    /* driver, device, and port-name strings follow wDefault */  
} DEVNAMES;  
```  
  
#### Parameter  
 *wDriverOffset*  
 \(Eingabe\/Ausgabe\) gibt den Offset in Zeichen an eine auf NULL endende Zeichenfolge, die den Dateinamen \(ohne Dateinamenerweiterung\) des Gerätetreibers enthält.  Bei Eingabe wird diese Zeichenfolge verwendet, um den Drucker zu bestimmen, der im Dialogfeld ursprünglich angezeigt.  
  
 *wDeviceOffset*  
 \(Eingabe\/Ausgabe\) gibt den Offset in Zeichen auf NULL endende Zeichenfolge an \(Maximum von 32 Bytes einschließlich die NULL\) die den Namen des Geräts enthält.  Diese Zeichenfolge muss dem **dmDeviceName**\-Member der [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565)\-Struktur identisch sein.  
  
 *wOutputOffset*  
 \(Eingabe\/Ausgabe\) gibt den Offset in Zeichen auf NULL endende Zeichenfolge, die den DOS\-Gerätenamen für den physischen Ausgabemedium \(Ausgabeanschluss\) enthält.  
  
 *wDefault*  
 Gibt an, ob die Zeichenfolgen, die in der `DEVNAMES`\-Struktur enthalten sind, den Standarddrucker identifizieren.  Diese Zeichenfolge wird verwendet, um sicherzustellen, dass der nicht als Standarddrucker der letzte Druckvorgang geändert hat.  Bei Eingabe wenn das Flag **DN\_DEFAULTPRN** festgelegt ist, werden die anderen Werte in der `DEVNAMES`\-Struktur vor den aktuellen Standarddrucker überprüft.  Wenn eine der Zeichenfolgen gleichen Sie nicht ab, wird eine Fehlermeldung angezeigt, die Benutzer informierend, dass das Dokument z umformatiert werden muss.  Bei Ausgabe wird der **wDefault**\-Member nur geändert, wenn das Drucks\-Setupdialogfeld angezeigt wurde und der Benutzer die Schaltfläche OK ausgewählt.  Das **DN\_DEFAULTPRN**\-Flag wird festgelegt, wenn der Standarddrucker ausgewählt wurde.  Wenn ein bestimmter Drucker ausgewählt, wird das Flag nicht festgelegt.  Alle anderen Bits in diesem Member werden zur internen Verwendung durch die Druckdialogfeldfeldprozedur reserviert.  
  
## Hinweise  
 Die **PrintDlg**\-Funktion verwendet diese Zeichenfolgen, um Member im systemdefiniertem Drucken zu initialisieren.  Wenn der Benutzer das Dialogfeld geschlossen wird, werden Informationen über den ausgewählten Drucker in der Struktur zurückgegeben.  
  
## Anforderungen  
 **Header:** commdlg.h  
  
## Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CPrintDialog::CreatePrinterDC](../Topic/CPrintDialog::CreatePrinterDC.md)