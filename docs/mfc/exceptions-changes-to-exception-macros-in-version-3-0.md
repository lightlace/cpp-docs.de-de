---
title: "Ausnahmen: &#196;nderungen f&#252;r Ausnahmemakros in Version 3.0"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C++-Ausnahmebehandlung, Überlegungen zum Upgrade"
  - "CATCH-Makro"
  - "Ausnahmen, Neues"
  - "THROW_LAST-Makro"
ms.assetid: 3aa20d8c-229e-449c-995c-ab879eac84bc
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Ausnahmen: &#196;nderungen f&#252;r Ausnahmemakros in Version 3.0
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dies ist ein fortgeschrittenes Thema.  
  
 In MFC, Version 3.0 sind die Ausnahmebehandlungsmakros geändert, dass C\+\+\-Ausnahmen zu verwenden.  Dieser Artikel übermittelt, wie die Änderungen das Verhalten des vorhandenen Codes beeinflussen können, der die Makros verwendet.  
  
 Dieser Artikel enthält die folgenden Themen:  
  
-   [Ausnahmetypen und das ERFASSUNGSmakro](#_core_exception_types_and_the_catch_macro)  
  
-   [Erneute auslösen von Ausnahmen](#_core_re.2d.throwing_exceptions)  
  
##  <a name="_core_exception_types_and_the_catch_macro"></a> Ausnahmetypen und das ERFASSUNG Makro  
 In früheren Versionen von MFC, verwendet das **CATCH**\-Makro MFC\-Ablauftypinformationen, um einen Ausnahmetyp zu bestimmen; der Ausnahmetyp wird, d, mit der Übergabe bestimmt.  Mit C\+\+\-Ausnahmen jedoch wird der Typ der Ausnahme immer an der Wurfssite durch den Typ des Ausnahmeobjekts bestimmt, das ausgelöst wird.  Dies verursacht Inkompatibilitäten in dem seltenen Fall, in dem der Typ des Zeigers auf ausgelösten Objekt vom Typ der ausgelösten Objekts unterscheidet.  
  
 Im folgenden Beispiel wird die Auswirkung dieses Unterschieds zwischen MFC 3.0 und früheren Versionen:  
  
 [!CODE [NVC_MFCExceptions#1](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCExceptions#1)]  
  
 Dieser Code verhält sich anders in Version 3.0, da Steuerelement immer dem ersten **catch** \-Block mit einer entsprechenden AusnahmeDeklaration übergibt.  Das Ergebnis des Wurfsausdrucks  
  
 [!CODE [NVC_MFCExceptions#19](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCExceptions#19)]  
  
 wird als **CException\*** ausgelöst, obwohl mit **CCustomException** erstellt wird.  Das **CATCH**\-Makro in MFC\-Versionen 2.5 und in der vorherigen Verwendung `CObject::IsKindOf`, den Typ zur Laufzeit testen.  Da der Ausdruck  
  
 [!CODE [NVC_MFCExceptions#20](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCExceptions#20)]  
  
 gilt, die ersten catch\-Blocks\-Erfassungen die Ausnahme.  In Version 3.0, die verwendet C\+\+\-Ausnahmen, um viele der Ausnahmebehandlungsmakros zu implementieren, wird der zweite catch\-Block ausgelöste `CException` ab.  
  
 Code so ist selten.  Sie wird normalerweise, wenn ein Ausnahmeobjekt zu einer anderen Funktion, die generische **CException\*** akzeptiert, führt "bestimmte VorTHROW" und Auslösens schließlich die Ausnahme übergeben wird.  
  
 Um dieses Problem umgehen, den Wurfsausdruck der Funktion auf den Aufrufcode verschieben und eine Ausnahme auslösen des tatsächlichen Typs bezeichnet den Compiler, als die Ausnahme generiert wird.  
  
##  <a name="_core_re.2d.throwing_exceptions"></a> Erneute auslösen von Ausnahmen  
 Ein catch\-Block kann denselben Ausnahmezeiger nicht auslösen, den er abfing.  
  
 Beispielsweise wurde dieser Code in früheren Versionen gültig, wird jedoch unerwartete Ergebnisse mit Version 3.0 haben:  
  
 [!CODE [NVC_MFCExceptions#2](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCExceptions#2)]  
  
 Mit **THROW** im catch\-Block wird der Zeiger `e` gelöscht werden, um die äußere Übergabe eines ungültigen Zeigers empfängt.  Verwenden Sie `THROW_LAST`, `e` erneut ausgelöst.  
  
 Weitere Informationen finden Sie unter [Ausnahmen: Ausnahmen abfangen und Löschen](../mfc/exceptions-catching-and-deleting-exceptions.md).  
  
## Siehe auch  
 [Ausnahmebehandlung](../mfc/exception-handling-in-mfc.md)