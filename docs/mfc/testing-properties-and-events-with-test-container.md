---
title: "Testen der Eigenschaften und Ereignisse mit Test Container"
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
  - "ActiveX-Steuerelementtestcontainer"
  - "ActiveX-Steuerelemente [C++], Testen"
  - "Debuggen von ActiveX-Steuerelementen"
  - "Eigenschaften [MFC], Testen"
  - "Testcontainer"
  - "Testen, Testcontainer"
  - "tstcon32.exe"
ms.assetid: 626867cf-fe53-4c30-8973-55bb93ef3917
caps.latest.revision: 13
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Testen der Eigenschaften und Ereignisse mit Test Container
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Testcontainer\-Anwendung, bis in Visual C\+\+, ist ein ActiveX\-Steuerelementcontainer zum Testen und Debuggen von ActiveX\-Steuerelementen.  Testcontainer ermöglicht es dem Entwickler, um die Funktionalität des Steuerelements zu testen, indem er seine Eigenschaften ändert aufruft, Methoden, und die Ereignisse auslöst.  Testcontainer kann Protokolle der Datenbindungsbenachrichtigungen anzeigen und enthält außerdem Funktionen zum Testen einer Persistenzfunktionalität des ActiveX\-Steuerelements bereit: Sie können Eigenschaften in einen Stream oder dem substorage sichern, sie erneut laden und die gespeicherten Streamdaten überprüfen.  Dieser Abschnitt beschreibt, wie Sie die grundlegenden Features des Testcontainers verwendet.  Weitere Informationen auf das Menü **Hilfe** beim Durchführen des Testcontainers aus.  
  
### Um auf den Testcontainer für ActiveX\-Steuerelemente zugreifen  
  
1.  Erstellen Sie [TSTCON\-Beispiel: Testcontainer für ActiveX\-Steuerelemente](../top/visual-cpp-samples.md).  
  
### Um das ActiveX\-Steuerelement testen  
  
1.  Klicken Sie im Menü **Bearbeiten**  des Testcontainers, auf **Neues Steuerelement einfügen**.  
  
2.  Im Feld **Steuerelement einfügen**  auf das gewünschte Steuerelement aus und klicken auf **OK**.  Das Steuerelement wird im Steuerelementcontainer.  
  
    > [!NOTE]
    >  Wenn das Steuerelement nicht im Dialogfeld **Steuerelement einfügen** aufgeführt ist, stellen Sie sicher, mit dem Befehl **Steuerelemente registrieren** im Menü **Datei** des Testcontainers registriert haben.  
  
 An diesem Punkt können Sie die Eigenschaften oder die Ereignisse des Steuerelements testen.  
  
#### So testen Eigenschaften  
  
1.  Klicken Sie im Menü **Steuerelement**  auf **Methoden aufrufen**.  
  
2.  In der Dropdownliste **Methodenname** wählen Sie die PropPut\-Methode für die Eigenschaft aus, die Sie testen möchten.  
  
3.  Ändern Sie **Parameterwert** oder **Parametertyp** und klicken Sie auf der Schaltfläche **Wert festgelegt**.  
  
4.  Klicken Sie auf **Aufrufen** , um den neuen Wert das Objekt anzuwenden.  
  
     Die Eigenschaft enthält nun den neuen Wert.  
  
#### Um Ereignisse testen und das Ziel der Ereignisinformationen angeben.  
  
1.  Klicken Sie im Menü **Optionen**  auf **Protokollierung**.  
  
2.  Geben Sie das Ziel von Ereignisinformationen.  
  
## Siehe auch  
 [MFC\-ActiveX\-Steuerelemente](../mfc/mfc-activex-controls.md)   
 [Gewusst wie: Debuggen von ActiveX\-Steuerelementen](../Topic/How%20to:%20Debug%20an%20ActiveX%20Control.md)