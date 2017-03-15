---
title: "Handler f&#252;r Windows-Standardmeldungen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "afx_msg"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Funktionen [C++], Handler"
  - "Handlerfunktionen, Standard-Windows-Meldung"
  - "Meldungsbehandlung [C++], Windows-Meldungshandler"
  - "Nachrichten [C++], Windows"
  - "Windows-Nachrichten [C++], Handler"
ms.assetid: 19412a8b-2c38-4502-81da-13c823c7e36c
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Handler f&#252;r Windows-Standardmeldungen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Standardhandler für Standardwindows\-meldungen \(**WM\_**\) werden in der Klasse `CWnd` vordefinierten.  Die Klassenbibliothek basiert Namen für diese Handler auf dem Meldungsnamen.  Beispielsweise wird der Handler für `WM_PAINT` die Meldung wie in `CWnd` deklariert:  
  
 `afx_msg void OnPaint();`  
  
 Das Schlüsselwort **afx\_msg** schlägt die Auswirkungen des Schlüsselworts C\+\+ **virtuell** vor, indem die Handler von anderen Memberfunktionen `CWnd` unterscheidet.  Beachten Sie jedoch dass diese Funktionen nicht tatsächlich virtuell sind; sie werden stattdessen durch Meldungszuordnungen implementiert.  Meldungszuordnungen hängen nur von den Standardpräprozessormakros, nicht aus allen möglichen Erweiterungen zur Programmiersprache C\+\+ ab.  Das Schlüsselwort **afx\_msg** löst zum Leerstellen auf, nachdem es vorverarbeitet hat.  
  
 Um einen Handler zu überschreiben, der in einer Basisklasse definiert ist, definieren Sie eine Funktion mit demselben Prototyp in der abgeleiteten Klasse und einen Eintrag in der Meldungszuordnung für den Handler zu machen.  Der Handler "überschreibt" jeden Handler des gleichen Namens in einem aus Basisklassen der Klasse.  
  
 In bestimmten Fällen sollte Ihr Handler den überschriebenen Handler in der Basisklasse aufrufen, sodass die Basisklasse und Windows die Meldung angewendet werden.  Wo Sie aufrufen, hängt der Basisklassenhandler in der Überschreibung von den Umständen ab.  Manchmal müssen Sie den Handler zuerst und manchmal zuletzt aufrufen.  Manchmal wird der Basisklassenhandler bedingt auf, wenn Sie festlegen, dass die Meldung nicht bearbeiten können.  Gelegentlich soll der Basisklassenhandler aufrufen, dann, bedingt eigenen Handlercode, je nach Wert oder dem Zustand auszuführen, die vom Handler zurückgegeben werden.  
  
> [!CAUTION]
>  Es ist nicht sicher, die Argumente zu ändern, die in einen Handler übergeben werden, wenn Sie beabsichtigen, diese in einen Handler zu übergeben.  Beispielsweise verwenden Sie Möglicherweise werden, um das `nChar`\-Argument des Handlers `OnChar` zu ändern \(in Großbuchstaben konvertiert, beispielsweise\).  Dieses Verhalten ist, aber recht dunkel, wenn Sie diesen Effekt erledigen müssen, verwendet die `CWnd`\-Memberfunktion stattdessen **SendMessage**.  
  
 So bestimmen Sie die korrekte Methode, eine bestimmte Meldung zu überschreiben?  Wenn das Eigenschaftenfenster das Skelett der Handlerfunktion für eine bestimmte Meldung schreibt ein `OnCreate`\-Handler für `WM_CREATE`, z \- er beschrieben in Form der empfohlenen überschriebenen Memberfunktion.  Im folgenden Beispiel wird Handlererste dass der ruf der Basisklassenhandler und wird nur unter der Bedingung, dass es erst beendet wird \- 1 fort.  
  
 [!CODE [NVC_MFCMessageHandling#3](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCMessageHandling#3)]  
  
 Konventionell beginnen die Namen dieser Handler mit dem Präfix "an." Einige dieser Handler nehmen keine Argumente, während andere mehrere nehmen.  Einigen auch einen Rückgabetyp als `void`.  Der Standardhandler für alle **WM\_** Meldungen werden in der *MFC\-Referenz* als Memberfunktionen der Klasse `CWnd` dokumentiert, deren Namen beginnen mit "." Die Memberfunktionsdeklarationen in `CWnd` werden mit **afx\_msg** vorangestellt.  
  
## Siehe auch  
 [Deklarieren von Meldungshandlerfunktionen](../mfc/declaring-message-handler-functions.md)