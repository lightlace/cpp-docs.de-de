---
title: "ActiveX-Steuerelementcontainer: Programmieren von ActiveX-Steuerelementen in einem ActiveX-Steuerelementcontainer"
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
  - "ActiveX-Steuerelementcontainer [C++], Zugreifen auf ActiveX-Steuerelemente"
  - "ActiveX-Steuerelementcontainer [C++], Wrapperklassen"
  - "ActiveX-Steuerelemente [C++], Aufrufen"
  - "ActiveX-Steuerelemente [C++], Wrapperklassen"
  - "Confirm Classes-Dialogfeld"
  - "Headerdateien [C++], für ActiveX-Steuerelement-Wrapperklasse"
  - "MFC ActiveX-Steuerelemente [C++], Zugreifen in Containern"
  - "Wrapperklassen [C++], ActiveX-Steuerelemente"
  - "Wrapperklassen [C++], Verwenden"
ms.assetid: ef9b2480-92d6-4191-b16e-8055c4fd7b73
caps.latest.revision: 8
caps.handback.revision: "4"
ms.author: "mblome"
manager: "ghogen"
---
# ActiveX-Steuerelementcontainer: Programmieren von ActiveX-Steuerelementen in einem ActiveX-Steuerelementcontainer
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Artikel beschreibt das Verfahren zum Zugriff verfügbar gemachte [Methoden](../mfc/mfc-activex-controls-methods.md) und im [Eigenschaften](../mfc/mfc-activex-controls-properties.md) von eingebetteten ActiveX\-Steuerelemente.  Grundsätzlich führen Sie folgende Schritte aus:  
  
1.  [Fügen Sie ein ActiveX\-Steuerelement in das ActiveX\-Containerprojekt ein](../mfc/inserting-a-control-into-a-control-container-application.md) mithilfe des Katalogs.  
  
2.  [Definieren Sie eine Membervariable](../mfc/activex-control-containers-connecting-an-activex-control-to-a-member-variable.md) \(oder ein anderes Formular des Zugriffs\) desselben Typs als die ActiveX\-Steuerelement\-Wrapperklasse ein.  
  
3.  [Programmieren Sie das ActiveX\-Steuerelement](#_core_programming_the_activex_control) mithilfe vordefinierter Memberfunktionen der Wrapperklasse.  
  
 Für diese Diskussion wird angenommen, dass Sie ein dialogfeldbasiertes Projekt \(mit dem Namen bin\) mit ActiveX\-Steuerelement\-Unterstützung erstellt haben.  Das Circ\-Beispielsteuerelement, Circ, wird dem resultierenden Projekt hinzugefügt.  
  
 Sobald das Circ\-Steuerelement in das Projekt eingefügt wird \(Schritt 1\), fügen eine Instanz des Circ\-Steuerelements im Hauptdialogfeld der Anwendung ein.  
  
## Prozeduren  
  
#### Um dem Circ\-Steuerelement der Dialogfeldvorlage hinzufügen  
  
1.  Laden Sie das ActiveX\-Steuerelement\-Containerprojekt.  Verwenden Sie beispielsweise das Projekt `Container`.  
  
2.  Klicken Sie auf die Registerkarte Ressourcenansicht.  
  
3.  Öffnen Sie den Ordner **Dialogfeld**.  
  
4.  Doppelklicken Sie auf die Hauptdialogfeldvorlage.  Verwenden Sie beispielsweise **IDD\_CONTAINER\_DIALOG**.  
  
5.  Klicken Sie auf das Circ\-Steuersymbol in der Toolbox.  
  
6.  Klicken Sie auf eine Stelle innerhalb des Dialogfelds, um das Circ\-Steuerelement einzufügen.  
  
7.  Wählen Sie im Menü **Datei** wählen Sie **Alle speichern**, um alle Änderungen der Dialogfeldvorlage zu speichern.  
  
## Änderungen zum Projekt  
 Um die Containeranwendung zu aktivieren auf das Circ\-Steuerelement zuzugreifen, fügt Visual C\+\+ dem Containerprojekt automatisch die Implementierungsdatei \(.CPP\) der Wrapperklasse \(`CCirc`\) und der Dialogfeldheaderdatei die Wrapperklassenkopfzeile \(.H\) Datei hinzu:  
  
 [!CODE [NVC_MFC_AxCont#1](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxCont#1)]  
  
##  <a name="_core_the_wrapper_class_header_28h29_file"></a> Die Wrapperklassen\-Kopfzeile \(.H\) Datei  
 Um Eigenschaften \(und Methoden aufrufen\) für das Circ\-Steuerelement abzurufen und festzulegen, stellt die `CCirc` \- Wrapperklasse eine Deklaration aller verfügbar gemachten Methoden und Eigenschaften.  Im Beispiel werden diese Deklarationen in CIRC.H. gefunden.  Das folgende Beispiel ist Teil der `CCirc`\-Klasse, die verfügbar gemachten Schnittstellen des ActiveX\-Steuerelements definiert:  
  
 [!CODE [NVC_MFC_AxCont#2](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxCont#2)]  
[!CODE [NVC_MFC_AxCont#3](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxCont#3)]  
  
 Diese Features können von der anderer Prozeduren der Anwendung mit normaler C\+\+\-Syntax dann aufgerufen werden.  Weitere Informationen zur Verwendung dieser Memberfunktion, die festgelegt wird, um auf die Methoden und Eigenschaften des Steuerelements zugreifen, finden Sie im Abschnitt [Programmierung des ActiveX\-Steuerelements](#_core_programming_the_activex_control).  
  
##  <a name="_core_member_variable_modifications_to_the_project"></a> Membervariablen\-Änderungen zum Projekt  
 Sobald das ActiveX\-Steuerelement dem Projekt hinzugefügt wurde und in einem Dialogfeldcontainer eingebettet wurde, kann darauf von anderen Teilen des Projekts zugegriffen werden.  Die einfachste Möglichkeit, auf das Steuerelement zugegriffen wird [erstellen Sie eine Membervariable](../mfc/activex-control-containers-connecting-an-activex-control-to-a-member-variable.md) der Dialogklasse, `CContainerDlg` \(Schritt 2\), der vom gleichen Typ wie die Wrapperklasse handelt, die dem Projekt von Visual C\+\+ wird hinzugefügt.  Sie können die Membervariable dann verwenden, um auf das eingebettete Steuerelement jederzeit zuzugreifen.  
  
 Wenn das Dialogfeld der `m_circctl`**Membervariable hinzufügen**\-Membervariable dem Projekt hinzugefügt, wird auch die folgenden Zeilen hinzu der Headerdatei \(.H\) der `CContainerDlg`\-Klasse:  
  
 [!CODE [NVC_MFC_AxCont#4](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxCont#4)]  
[!CODE [NVC_MFC_AxCont#5](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxCont#5)]  
  
 Außerdem wird ein Aufruf **DDX\_Control** automatisch der `CContainerDlg` Implementierung von `DoDataExchange` hinzugefügt:  
  
 [!CODE [NVC_MFC_AxCont#6](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxCont#6)]  
  
##  <a name="_core_programming_the_activex_control"></a> Programmierung des ActiveX\-Steuerelements  
 Sie haben jetzt das ActiveX\-Steuerelement in der Dialogfeldvorlage eingefügt und eine Membervariable für diese erstellt.  Sie können allgemeine C\+\+\-Syntax jetzt verwenden, um die auf Eigenschaften und Methoden des eingebetteten Steuerelements zuzugreifen.  
  
 Als bekannte \(in [Die Wrapperklassen\-Kopfzeile \(.H\) Datei](#_core_the_wrapper_class_header_28h29_file)\), die Headerdatei \(.H\) für die `CCirc` \- Wrapperklasse, in diesem Fall CIRC.H, enthält eine Liste mit Memberfunktionen, die Sie verwenden können, um jeden verfügbar gemachte Eigenschaft abzurufen und festzulegen.  Memberfunktionen für verfügbar gemachte Methoden sind auch verfügbar.  
  
 Ein allgemeiner Position, an der Eigenschaften des Steuerelements zu ändern ist in der `OnInitDialog`\-Memberfunktion der Hauptdialogfeldklasse.  Diese Funktion wird, bevor das Dialogfeld angezeigt wird und verwendet wird, um den Inhalt zu initialisieren, einschließlich seiner Steuerelemente bezeichnet.  
  
 Das folgende Codebeispiel verwendet die `m_circctl`\-Membervariable, um die Beschriftungs\- und CircleShape\-Eigenschaften des eingebetteten Circ\-Steuerelements zu ändern:  
  
 [!CODE [NVC_MFC_AxCont#7](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxCont#7)]  
  
## Siehe auch  
 [ActiveX\-Steuerelementcontainer](../mfc/activex-control-containers.md)