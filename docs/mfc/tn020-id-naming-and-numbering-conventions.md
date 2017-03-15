---
title: "TN020: ID-Benennungs- und Nummerierungskonventionen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.id"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Ressourcenbezeichner"
  - "Ressourcenbezeichner, Benennen und Nummerieren"
  - "TN020"
ms.assetid: aecbd2cf-68b3-47f6-ae21-b1f507917245
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# TN020: ID-Benennungs- und Nummerierungskonventionen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In diesem Hinweis werden die Benennungs\- und \-Nummerierungskonventionen für IDs erläutert, die in MFC 2.0 für Ressourcen, Befehle, Zeichenfolgen, Steuerelemente und untergeordnete Fenster verwendet werden.  
  
 Die MFC\-Benennungs\- und \-Nummerierungskonventionen für IDs müssen folgende Anforderungen erfüllen:  
  
-   Bereitstellen eines konsistenten ID\-Benennungsstandards, der in den MFC\-Bibliotheken und MFC\-Anwendungen verwendet wird, die vom Visual C\+\+\-Ressourcen\-Editor unterstützt werden.  Damit kann der Programmierer den Typ und den Ursprung einer Ressource einfacher anhand seiner ID interpretieren.  
  
-   Hervorheben der engen 1:1\-Beziehung zwischen bestimmten Typen von IDs.  
  
-   Gewährleisten von Konformität mit bereits weit verbreiteten Standards für die Benennung von IDs in Windows.  
  
-   Partitionieren des ID\-Nummerierungsbereichs.  ID\-Nummern können vom Programmierer sowie von in MFC, Windows und Visual C\+\+ bearbeiteten Ressourcen zugewiesen werden.  Mit der entsprechenden Partitionierung kann die Duplizierungen von ID\-Nummern vermieden werden.  
  
## Die ID\-Präfix\-Namenskonvention  
 Einige ID\-Typen können in einer Anwendung auftreten.  Die MFC\-Benennungskonvention für ID definiert unterschiedliche Präfixe für unterschiedliche Ressourcentypen.  
  
 MFC verwendet das Präfix "IDR\_", um eine Ressourcen\-ID anzugeben, die für mehrere Ressourcentypen gilt.  So verwendet MFC z. B. in einem bestimmten Rahmenfenster dasselbe "IDR\_"\-Präfix, um eine Menü\-, Zugriffstasten\-, Zeichenfolgen\- und Symbolressource anzugeben.  In der folgenden Tabelle werden die verschiedenen Präfixe und ihre Verwendung aufgeführt:  
  
|Präfix|Verwendung|  
|------------|----------------|  
|IDR\_|Für mehrere Ressourcentypen \(wird hauptsächlich für Menüs, Zugriffstasten und Menübänder verwendet\).|  
|IDD\_|Für Ressourcen der Dialogfeldvorlage \(z. B. IDD\_DIALOG1\).|  
|IDC\_|Für Cursorressourcen.|  
|IDI\_|Für Symbolressourcen.|  
|IDB\_|Für Bitmapressourcen.|  
|IDS\_|Für Zeichenfolgenressourcen.|  
  
 Innerhalb einer DIALOG\-Ressource folgt MFC diesen Konventionen:  
  
|Präfix oder Bezeichnung|Verwendung|  
|-----------------------------|----------------|  
|IDOK, IDCANCEL|Für Standardschaltflächen\-IDs.|  
|IDC\_|Für andere Dialogfeld\-Steuerelemente.|  
  
 Das Präfix "IDC\_" wird auch für Cursor verwendet.  Dieser Namenskonflikt ist normalerweise kein Problem, da eine typische Anwendung über wenige Cursor und viele Dialogfeld\-Steuerelemente verfügt.  
  
 Innerhalb einer Menüressource folgt MFC diesen Konventionen:  
  
|Präfix|Verwendung|  
|------------|----------------|  
|IDM\_|Für Menüelemente, in denen nicht die MFC\-Befehlsarchitektur verwendet wird.|  
|ID\_|Für Menübefehle, in denen MFC\-Befehlsarchitektur verwendet wird.|  
  
 Befehle, die der MFC\-Befehlsarchitektur folgen, müssen einen `ON_COMMAND`\-Befehlshandler haben und können über einen `ON_UPDATE_COMMAND_UI`\-Handler verfügen.  Wenn diese Befehlshandler der MFC\-Befehlsarchitektur folgen, funktionieren sie unabhängig davon ordnungsgemäß, ob sie an einen Menübefehl, an eine Symbolleisten\-Schaltfläche oder an eine Dialogleisten\-Schaltfläche gebunden sind.  Das gleiche "ID\_"\-Präfix wird auch für eine Zeichenfolge in einer Menüeingabeaufforderung verwendet, die auf der Statusleiste des Programms angezeigt wird.  Die meisten Menüelemente in der Anwendung sollten den MFC\-Befehlskonventionen folgen.  Alle IDs für Standardbefehle \(z. B. `ID_FILE_NEW`\) entsprechen dieser Konvention.  
  
 MFC verwendet auch "IDP\_" als eine spezielle Form von Zeichenfolgen \(anstelle von "IDS\_"\).  Zeichenfolgen mit dem Präfix "IDP\_" sind Eingabeaufforderungen, d. h. Zeichenfolgen, die in Meldungsfeldern verwendet werden. "IDP\_"\-Zeichenfolgen können "%1" "und "%2" als Platzhalter für Zeichenfolgen enthalten, die vom Programm bestimmt werden. "IDP\_"\-Zeichenfolgen sind in der Regel Hilfethemen zugeordnet, während "IDS\_"\-Zeichenfolgen keine Hilfethemen zugeordnet sind. "IDP\_"\-Zeichenfolgen werden immer lokalisiert, und "IDS\_"\-Zeichenfolgen können nicht lokalisiert werden.  
  
 Die MFC\-Bibliothek verwendet auch das Präfix "IDW\_" als eine spezielle Form von Steuerelement\-IDs \(anstelle von "IDC\_"\).  Diese IDs werden durch die .NET\-Frameworkklassen untergeordneten Fenstern als Ansichten und Aufteilung zugewiesen.  IDs für MFC\-Implementierungen wird "AFX\_" vorangestellt.  
  
## Die ID\-Nummerierungskonvention  
 In der folgenden Tabelle werden die gültigen Bereiche für die IDs der bestimmten Typen aufgeführt.  Einige der Grenzen sind technische Implementierungsgrenzen und andere sind Konventionen, die entwickelt wurden, um zu verhindern, dass Konflikte zwischen den IDs und den von Windows vordefinierten IDs oder MFC\-Standardimplementierungen auftreten.  
  
 Es wird dringend empfohlen, dass Sie alle IDs innerhalb der empfohlenen Bereiche definieren.  Die Untergrenze dieser Bereiche ist 1, da 0 nicht verwendet wird.  Es wird empfohlen, die allgemeine Konvention einzuhalten, 100 oder 101 als erste ID zu verwenden.  
  
|Präfix|Ressourcentyp|Gültiger Bereich|  
|------------|-------------------|----------------------|  
|IDR\_|mehrere|1 bis 0x6FFF|  
|IDD\_|Dialogfeldvorlagen|1 bis 0x6FFF|  
|IDC\_,IDI\_,IDB\_|Cursor, Symbole, Bitmaps|1 bis 0x6FFF|  
|IDS\_, IDP\_|Allgemeine Zeichenfolgen|1 bis 0x7FFF|  
|ID\_|Befehle|0x8000 bis 0xDFFF|  
|IDC\_|Steuerelemente|8 bis 0xDFFF|  
  
 Gründe für diese Begrenzungen:  
  
-   Standardmäßig wird der ID\-Wert 0 nicht verwendet.  
  
-   Durch Einschränkungen der Windows\-Implementierung werden echte Ressourcen\-IDs auf einen Wert kleiner oder gleich 0x7FFF eingeschränkt.  
  
-   Das interne MFC\-Framework reserviert diese Bereiche:  
  
    -   0x7000 bis 0x7FFF \(siehe afxres.h\)  
  
    -   0xE000 bis 0xEFFF \(siehe afxres.h\)  
  
    -   16000 bis 18000 \(siehe afxribbonres.h\)  
  
     Diese Bereiche ändern sich möglicherweise in zukünftigen MFC\-Implementierungen.  
  
-   Einige Windows\-Systembefehle verwenden den Bereich von 0xF000 bis 0xFFFF.  
  
-   Steuerelemente\-IDs von 1 bis 7 sind für Standardsteuerelemente wie IDOK und IDCANCEL reserviert.  
  
-   Der Bereich von 0x8000 bis 0xFFFF für Zeichenfolgen ist für Befehle in Menüeingabeaufforderungen reserviert.  
  
## Siehe auch  
 [Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)