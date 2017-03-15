---
title: "Implementing a Window with CWindowImpl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CWindowImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL, Fenster"
  - "subclassing ATL window classes"
  - "superclassing, ATL"
  - "windows [C++], ATL"
  - "windows [C++], subclassing"
  - "windows [C++], superclassing"
ms.assetid: 3fc40550-f1d6-4702-8b7c-4cf682b6a855
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Implementing a Window with CWindowImpl
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Um ein Fenster zu implementieren, leiten Sie eine Klasse von `CWindowImpl`.  In der abgeleiteten Klasse deklarieren Sie eine Meldungszuordnung und die Meldungshandlerfunktionen.  Sie können die Klasse auf drei Arten jetzt verwenden:  
  
-   [Erstellen Sie ein Fenster auf Grundlage einer neue Windows\-Klasse erstellt](#_atl_creating_a_window_based_on_a_new_windows_class)  
  
-   [Übergeordnete Klasse eine vorhandene Windows\-Klasse](#_atl_superclassing_an_existing_windows_class)  
  
-   [Ordnen Sie ein vorhandenes Fenster unter](#_atl_subclassing_an_existing_window)  
  
##  <a name="_atl_creating_a_window_based_on_a_new_windows_class"></a> Erstellen eines Fensters auf Grundlage einer neue Windows\-Klasse  
 `CWindowImpl` enthält das [DECLARE\_WND\_CLASS](../Topic/DECLARE_WND_CLASS.md)\-Makro, um Windows\-Klasseninformationen zu deklarieren.  Dieses Makro implementiert die `GetWndClassInfo`\-Funktion, die [CWndClassInfo](../atl/reference/cwndclassinfo-class.md) verwendet, um Informationen einer neue Windows\-Klasse zu definieren.  Wenn `CWindowImpl::Create` aufgerufen wird, wird diese Windows\-Klasse registriert und ein neues Fenster wird erstellt.  
  
> [!NOTE]
>  `CWindowImpl` führt **NULL** zum `DECLARE_WND_CLASS`\-Makro, das bedeutet, dass ATL einen Windows\-Klassennamen generiert.  Um einen eigenen Namen anzugeben, übergeben Sie eine Zeichenfolge zu `DECLARE_WND_CLASS` im `CWindowImpl` von abgeleitete Klasse.  
  
## Beispiel  
 Das folgende Beispiel zeigt eine Klasse, die ein Fenster auf Grundlage einer neue Windows\-Klasse implementiert:  
  
 [!CODE [NVC_ATL_Windowing#64](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Windowing#64)]  
  
 Um ein Fenster zu erstellen, erstellen Sie eine Instanz von `CMyWindow` und rufen dann die **Create**\-Methode auf.  
  
> [!NOTE]
>  Um die Standardeinstellungen Windows\-Klasseninformationen zu überschreiben, implementieren Sie die `GetWndClassInfo`\-Methode in der abgeleiteten Klasse mit der `CWndClassInfo`\-Member auf die entsprechenden Werte festlegen.  
  
##  <a name="_atl_superclassing_an_existing_windows_class"></a> Erstellen einer übergeordneten Klasse für eine vorhandene Windows\-Klasse  
 Das [DECLARE\_WND\_SUPERCLASS](../Topic/DECLARE_WND_SUPERCLASS.md)\-Makro ermöglicht es Ihnen, ein Fenster erstellen, das übergeordnete Klasse eine vorhandene Windows\-Klasse.  Geben Sie dieses Makro im `CWindowImpl` von abgeleitete Klasse.  wie jedes andere ATL\-Fenster werden Meldungen durch eine Meldungszuordnung bearbeitet.  
  
 Wenn Sie `DECLARE_WND_SUPERCLASS` verwenden, wird eine neue Windows\-Klasse registriert.  Diese neue Klasse ist genauso, der die vorhandene Klasse Sie angeben, aber die Fensterprozedur durch `CWindowImpl::WindowProc` ersetzen werden \(oder mit einer Funktion, die diese Methode überschreibt\).  
  
## Beispiel  
 Das folgende Beispiel zeigt eine Klasse, die die übergeordnete Klasse Standard\-Bearbeiten\-Klasse:  
  
 [!CODE [NVC_ATL_Windowing#65](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Windowing#65)]  
  
 Um das zu Bearbeitungsfenster zu erstellen, erstellen Sie eine Instanz von `CMyEdit` und rufen dann die **Create**\-Methode auf.  
  
##  <a name="_atl_subclassing_an_existing_window"></a> Erstellen von Unterklassen von einem vorhandenen Fensters  
 Um ein vorhandenes Fenster unterzuordnen, leiten Sie eine Klasse von `CWindowImpl` und deklarieren Sie eine Meldungszuordnung, wie in den vorherigen zwei Fällen.  Beachten Sie jedoch die Sie keine Windows\-Klasseninformationen angeben, wie Sie ein bereits vorhandenes Fenster unterordnen.  
  
 Anstatt aufzurufen, **Create** auf, rufen Sie `SubclassWindow` und führen Sie es das Handle zum vorhandenen Fenster, das Sie unterordnen möchten.  Sobald das Fenster als Unterklasse definiert ist, wird `CWindowImpl::WindowProc` \(oder die Funktion, die diese Methode überschreibt\), um Meldungen auf die Meldungszuordnung zu verweisen.  Um ein untergeordnetes Fenster aus dem Objekt aufzuheben, rufen Sie `UnsubclassWindow` auf.  Die ursprüngliche Fensterprozedur des Fensters wird dann wiederhergestellt.  
  
## Siehe auch  
 [Implementing a Window](../atl/implementing-a-window.md)