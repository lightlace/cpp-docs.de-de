---
title: "CUserException Class"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "CUserException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CUserException class"
  - "Fehler [C++], Abfangen"
  - "Ausnahmen, Auslösen"
  - "operations [C++]"
  - "operations [C++], Anhalten"
  - "Auslösen von Ausnahmen, stopping user operations"
ms.assetid: 2156ba6d-2cce-415a-9000-6f02c26fcd7d
caps.latest.revision: 23
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# CUserException Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wird ausgelöst, um einen Endbenutzervorgang zu beenden.  
  
## Syntax  
  
```  
class CUserException : public CSimpleException  
```  
  
## Hinweise  
 Verwendung `CUserException`, wenn Sie den Wurfs\-\/Erfassungsausnahmemechanismus für anwendungsspezifische Ausnahmen verwenden möchten. "  Benutzer" im Klassennamen kann interpretiert werden, wie "My Benutzer Ausnahmes einige bereit, das ich behandeln muss".  
  
 `CUserException` wird normalerweise ausgelöst, nachdem die globale Funktion `AfxMessageBox` aufgerufen wurde, um den Benutzer zu benachrichtigen, dass ein Vorgang fehlgeschlagen ist.  Wenn Sie einen Ausnahmehandler schreiben, behandeln Sie die Ausnahme besonders, da der Benutzer normalerweise bereits vom Fehler benachrichtigt wurde.  Das Framework löst diese Ausnahme in einigen Fällen aus.  Um `CUserException` sich auszulösen, warnen Sie den Benutzer und rufen dann die globale Funktion `AfxThrowUserException` auf.  
  
 Im Beispiel unten, eine Funktion, die Vorgänge enthält, die möglicherweise Warnungen der Benutzer und auslöst `CUserException` belassen.  Die aufrufende Funktion wird die Ausnahme abgefangen und behandelt sie besonders:  
  
 [!CODE [NVC_MFCExceptions#24](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCExceptions#24)]  
  
 Weitere Informationen zur Verwendung von `CUserException`, finden Sie im Artikel [Ausnahmebehandlung \(MFC\)](../../mfc/exception-handling-in-mfc.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 [CSimpleException](../../mfc/reference/csimpleexception-class.md)  
  
 `CUserException`  
  
## Anforderungen  
 **Header:** afxwin.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CException Class](../../mfc/reference/cexception-class.md)   
 [AfxMessageBox](../Topic/AfxMessageBox.md)   
 [AfxThrowUserException](../Topic/AfxThrowUserException.md)   
 [Wie behebe ich: Erstellen Sie die eigenen benutzerdefinierten Ausnahme\-Klassen?](http://go.microsoft.com/fwlink/?LinkId=128045)