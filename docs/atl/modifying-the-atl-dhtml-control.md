---
title: "Modifying the ATL DHTML Control | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DHTML controls"
  - "DHTML controls, Ändern"
  - "HTML-Steuerelemente, Ändern"
ms.assetid: c053f35f-8629-4600-9595-721f5956777a
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Modifying the ATL DHTML Control
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der ATL\-Steuerelement\-Assistent stellt Startcode bereit, sodass das Steuerelement erstellen und ausführen und daher können Sie sehen, wie die Methoden in die Projektdateien geschrieben werden und wie die DHTML\-Aufrufe in den C\+\+\-Code des Steuerelements mithilfe der Dispatchmethoden.  Sie können jede Dispatchmethode der Schnittstelle hinzufügen.  Anschließend können Sie die Methoden in der HTML\-Ressource aufrufen.  
  
#### Um das Steuerelement ATL DHTML ändern  
  
1.  Erweitern Sie in der Klassenansicht das Steuerelementprojekt.  
  
     Beachten Sie die Schnittstelle, die in "Benutzeroberfläche" hat eine Methode beendet, `OnClick`.  Die Schnittstelle, die nicht in "Benutzeroberfläche" endet, hat keine Methoden.  
  
2.  Fügen Sie eine Methode hinzu, die `MethodInvoked` der Schnittstelle aufgerufen wird, die endet nicht in "Benutzeroberfläche."  
  
     Diese Methode wird auf die Schnittstelle, die im Steuerelementcontainer für Containerinteraktion verwendet wird, nicht zur \- Schnittstelle hinzugefügt, die von DHTML verwendet wird, um mit dem Steuerelement interagieren.  Nur der Container kann diese Methode aufrufen.  
  
3.  Suchen Sie die gerodete\-heraus Methode in der CPP\-Datei und fügen Sie Code hinzu, um ein Meldungsfeld anzuzeigen, beispielsweise:  
  
     [!CODE [NVC_ATL_COM#5](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_COM#5)]  
  
4.  Fügen Sie eine andere Methode hinzu, die `HelloHTML` aufgerufen wird, wird nur dieses Mal hinzufügen, es der dieser Schnittstelle Enden in "Benutzeroberfläche." Suchen Sie die gerodete\-heraus `HelloHTML`\-Methode in der CPP\-Datei und fügen Sie Code hinzu, um ein Meldungsfeld anzuzeigen, beispielsweise:  
  
     [!CODE [NVC_ATL_COM#6](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_COM#6)]  
  
5.  Fügen Sie eine dritte Methode, `GoToURL`, Schnittstelle hinzu, die endet nicht in "Benutzeroberfläche." Implementieren diese Methode durch Aufrufen von [IWebBrowser2::Navigate](https://msdn.microsoft.com/en-us/library/aa752133.aspx), wie folgt:  
  
     [!CODE [NVC_ATL_COM#7](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_COM#7)]  
  
     Sie können die **IWebBrowser2**\-Methoden verwenden, da ATL einen Zeiger auf diese Schnittstelle für Sie in der H\-Datei bereitstellt.  
  
 Als Nächstes ändern Sie die HTML\-Ressource, um die Methoden aufzurufen, die Sie erstellt haben.  Sie fügen drei Schaltflächen zum Aufrufen dieser Methoden hinzu.  
  
#### Um die HTML\-Ressource ändern  
  
1.  Klicken Sie im Projektmappen\-Explorer, doppelklicken Sie auf die Datei .htm\-, um die HTML\-Ressource anzuzeigen.  
  
     Überprüfen Sie das HTML, insbesondere die Aufrufe der externen Windows\-Dispatchmethoden.  Der HTML\-Code `OnClick` ruft die Methode des Projekts auf, und die Parameter geben den Text des Steuerelements \(`theBody`\) und Farbe an, um zuzuweisen `red`\(""\).  Der Text, der dem Methodenaufruf folgt, ist die Bezeichnung, die auf der Schaltfläche angezeigt wird.  
  
2.  Fügen Sie eine weitere Möglichkeit, nur `OnClick` Änderung die Farbe hinzu.  Beispiel:  
  
    ```  
    <br>  
    <br>  
    <BUTTON onclick='window.external.OnClick(theBody, "white");'>Refresh</BUTTON>  
    ```  
  
     Diese Methode erstellt eine Schaltfläche, **Aktualisieren** auf mit der Bezeichnung erstellt, das der Benutzer klicken kann, um das Steuerelement dem ursprünglichen, weißen Hintergrund zurückzugeben.  
  
3.  Fügen Sie den Aufruf der `HelloHTML`\-Methode hinzu, die Sie erstellt haben.  Beispiel:  
  
    ```  
    <br>  
    <br>  
    <BUTTON onclick='window.external.HelloHTML();'>HelloHTML</BUTTON>  
    ```  
  
     Diese Methode erstellt eine Schaltfläche, **HelloHTML** auf mit der Bezeichnung erstellt, das der Benutzer klicken kann, um das `HelloHTML` Meldungsfeld anzuzeigen.  
  
 Sie können jetzt erstellen und [testen Sie das geänderte DHTML\-Steuerelement](../atl/testing-the-modified-atl-dhtml-control.md).  
  
## Siehe auch  
 [Unterstützung für DHTML\-Steuerelemente](../atl/atl-support-for-dhtml-controls.md)