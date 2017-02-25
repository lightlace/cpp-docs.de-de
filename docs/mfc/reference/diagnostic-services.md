---
title: "Diagnosedienste | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.macros"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Diagnose, Diagnosefunktionen und Variablen"
  - "Diagnose, Diagnosedienste"
  - "Diagnose, Liste allgemeiner MFC"
  - "Diagnosefunktionen und Variablen"
  - "Diagnosemakros"
  - "Diagnosemakros, Liste allgemeiner MFC"
  - "Diagnosedienste"
  - "Diagnose, Diagnosefunktionen und Variablen"
  - "Diagnose, Diagnosedienste"
  - "Diagnose, Liste allgemeiner MFC"
  - "Allgemeine Diagnosefunktionen und Variablen"
  - "Allgemeine Diagnosemakros in MFC"
  - "MFC, Diagnosedienste"
  - "Objektdiagnosefunktionen in MFC"
  - "Dienste, Diagnose"
ms.assetid: 8d78454f-9fae-49c2-88c9-d3fabd5393e8
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# Diagnosedienste
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Microsoft Foundation Class\-Bibliothek bietet viele Diagnosedienste, die das Debuggen von Programmen erleichtern. Zu diesen Diagnosediensten zählen Makros und globale Funktionen, die Ihnen das Nachverfolgen der Speicherzuweisungen von Programmen, das Sichern des Inhalts von Objekten zur Laufzeit und das Ausgeben von Debugmeldungen zur Laufzeit ermöglichen. Die Makros und globalen Funktionen für Diagnosedienste sind in folgende Kategorien gruppiert:  
  
-   Allgemeine Diagnosemakros  
  
-   Allgemeine Diagnosefunktionen und \-Variablen  
  
-   Objektdiagnosefunktionen  
  
 Diese Makros und Funktionen stehen in den Debug\- und den endgültigen Produktversionen von MFC für alle von `CObject` abgeleiteten Klassen zur Verfügung. Mit Ausnahme von `DEBUG_NEW` und **VERIFY** führt jedoch keine von ihnen in der endgültigen Produktversion eine Aktion aus.  
  
 In der Debugbibliothek stehen alle zugewiesenen Speicherblöcke in aus einer Reihe von "Wächterbytes" bestehenden Klammern. Wenn diese Bytes durch einen fehlerhaften Schreibzugriff auf den Speicher gestört werden, können die Diagnoseroutinen ein Speicherproblem melden. Wenn Sie diese Zeile:  
  
 [!CODE [NVC_MFCCObjectSample#14](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCCObjectSample#14)]  
  
 in Ihre Implementierungsdatei einschließen, werden für jeden Aufruf von **new** der Dateiname und die Zeilennummer gespeichert, für die die Speicherzuweisung erfolgt ist. Die Funktion [CMemoryState::DumpAllObjectsSince](../Topic/CMemoryState::DumpAllObjectsSince.md) zeigt diese Zusatzinformationen an, was Ihnen das Erkennen von Speicherverlusten ermöglicht. Weitere Informationen zur Diagnoseausgabe finden Sie auch bei der Klasse [CDumpContext](../../mfc/reference/cdumpcontext-class.md).  
  
 Darüber hinaus unterstützt die C\-Laufzeitbibliothek auch eine Reihe von Diagnosefunktionen, die Sie zum Debuggen von Anwendungen verwenden können. Weitere Informationen finden Sie unter [Debugroutinen](../../c-runtime-library/debug-routines.md) in der Referenz zur Laufzeitbibliothek.  
  
### Allgemeine MFC\-Diagnosemakros  
  
|||  
|-|-|  
|[ASSERT](../Topic/ASSERT%20\(MFC\).md)|Gibt eine Meldung aus und bricht dann das Programm ab, wenn der angegebene Ausdruck in der Debugversion der Bibliothek als **FALSE** ausgewertet wird.|  
|[ASSERT\_KINDOF](../Topic/ASSERT_KINDOF.md)|Prüft, ob ein Objekt ein Objekt der angegebenen Klasse oder einer aus der angegebenen Klasse abgeleiteten Klasse ist.|  
|[ASSERT\_VALID](../Topic/ASSERT_VALID.md)|Prüft die interne Gültigkeit eines Objekts durch Aufrufen seiner `AssertValid`\-Memberfunktion; normalerweise durch `CObject` außer Kraft gesetzt.|  
|[DEBUG\_NEW](../Topic/DEBUG_NEW.md)|Gibt einen Dateinamen und eine Zeilennummer für alle Objektzuweisungen im Debugmodus an, um die Suche nach Speicherverlusten zu unterstützen.|  
|[DEBUG\_ONLY](../Topic/DEBUG_ONLY.md)|Ähnlich wie **ASSERT**, prüft jedoch nicht den Wert des Ausdrucks; nützlich für Code, der nur im Debugmodus ausgeführt werden soll.|  
|[TRACE](../Topic/TRACE.md)|Stellt eine `printf`\-ähnliche Funktionalität in der Debugversion der Bibliothek zur Verfügung.|  
|[VERIFY](../Topic/VERIFY.md)|Ähnlich wie **ASSERT**, wertet den Ausdruck aber sowohl in der endgültigen Version der Bibliothek als auch in der Debugversion aus.|  
  
### Allgemeine MFC\-Diagnosevariablen und \-Funktionen  
  
|||  
|-|-|  
|[afxDump](../Topic/afxDump%20\(CDumpContext%20in%20MFC\).md)|Globale Variable, die [CDumpContext](../../mfc/reference/cdumpcontext-class.md)\-Informationen an das Debuggerausgabefenster oder das Debugterminal sendet.|  
|[afxMemDF](../Topic/afxMemDF.md)|Globale Variable, die das Verhalten der Debugspeicherzuweisung steuert.|  
|[AfxCheckError](../Topic/AfxCheckError.md)|Globale Variable, die zum Prüfen des übergebenen **SCODE**s verwendet wird, um festzustellen, ob es sich um einen Fehler handelt; löst in diesem Fall den entsprechenden Fehler aus.|  
|[AfxCheckMemory](../Topic/AfxCheckMemory.md)|Überprüft die Integrität des gesamten derzeit zugewiesenen Speichers.|  
|[AfxDump](../Topic/AfxDump%20\(MFC\).md)|Sichert bei einem Aufruf im Debugger den Status eines Objekts während des Debuggens.|  
|[AfxDumpStack](../Topic/AfxDumpStack.md)|Generiert ein Image des aktuellen Stapels. Diese Funktion wird immer statisch gelinkt.|  
|[AfxEnableMemoryLeakDump](../Topic/AfxEnableMemoryLeakDump.md)|Ermöglicht das Sichern von Speicherverlusten.|  
|[AfxEnableMemoryTracking](../Topic/AfxEnableMemoryTracking.md)|Aktiviert und deaktiviert die Arbeitsspeicher\-Nachverfolgung.|  
|[AfxIsMemoryBlock](../Topic/AfxIsMemoryBlock.md)|Überprüft, ob ein Speicherblock ordnungsgemäß zugewiesen wurde.|  
|[AfxIsValidAddress](../Topic/AfxIsValidAddress.md)|Überprüft, ob ein Speicheradressbereich innerhalb der Grenzen des Programms liegt.|  
|[AfxIsValidString](../Topic/AfxIsValidString.md)|Bestimmt, ob ein Zeiger auf eine Zeichenfolge gültig ist.|  
|[AfxSetAllocHook](../Topic/AfxSetAllocHook.md)|Ermöglicht das Aufrufen einer Funktion für jede Speicherzuweisung.|  
  
### MFC\-Objektdiagnosefunktionen  
  
|||  
|-|-|  
|[AfxDoForAllClasses](../Topic/AfxDoForAllClasses.md)|Führt eine angegebene Funktion für alle von `CObject` abgeleiteten Klassen aus, die Typprüfung zur Laufzeit unterstützen.|  
|[AfxDoForAllObjects](../Topic/AfxDoForAllObjects.md)|Führt eine angegebene Funktion für alle von `CObject` abgeleiteten Objekte aus, die mithilfe von **new** zugewiesen wurden.|  
  
## Siehe auch  
 [MFC\-Makros, globale Funktionen und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)