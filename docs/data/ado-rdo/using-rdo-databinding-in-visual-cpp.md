---
title: "Verwenden der RDO-Datenbindung in Visual&#160;C++"
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
  - "Datenbindung [C++], RDO"
  - "RDO [C++], Datenbindung"
  - "RDO-Remote-Datensteuerelement, Binden von Daten in Visual C++"
  - "RemoteData-Steuerelement, Binden von Daten in Visual C++"
ms.assetid: 02b9cfe7-7bbe-4a01-b075-e28d9536ac4b
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Verwenden der RDO-Datenbindung in Visual&#160;C++
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Verwendung der RDO\-Datenbindung in Visual C\+\+ setzt voraus, dass Sie ein RDO\-Remote\-Datensteuerelement hinzufügen und auf eine Datenquelle sowie eine Datensatzquelle \(SQL\-Abfrage\) verweisen.  Außerdem müssen Sie ein datengebundenes RDO\-Steuerelement hinzufügen, dieses auf ein RDO\-Remote\-Datensteuerelement zeigen lassen und die Felder auswählen, die an die Datensatzquelle des RDO\-Remote\-Datensteuerelements gebunden werden sollen.  
  
### So verwenden Sie die RDO\-Datenbindung in Visual C\+\+  
  
1.  Konfigurieren Sie eine [ODBC\-Datenquelle](../../data/ado-rdo/odbc-connections.md), falls dies noch nicht geschehen ist.  
  
2.  Erstellen Sie mit dem MFC\-Anwendungs\-Assistenten eine auf Dialogfeldern oder auf einer Formularansicht basierende MFC\-Anwendung.  
  
3.  Fügen Sie dem Dialogfeld das Microsoft Remote\-Datensteuerelement \(RDO\-Remote\-Datensteuerelement\) hinzu. Siehe [Einfügen des Steuerelements in eine Visual C\+\+\-Anwendung](../../data/ado-rdo/inserting-the-control-into-a-visual-cpp-application.md).  
  
4.  Lassen Sie das RDO\-Remote\-Datensteuerelement auf die ODBC\-Datenquelle zeigen.  
  
    1.  Klicken Sie mit der rechten Maustaste auf das Steuerelement, und klicken Sie dann auf **Eigenschaften**.  
  
    2.  Klicken Sie auf die Registerkarte **Steuerelement**.  
  
    3.  Legen Sie als **DataSource** die ODBC\-Datenquelle fest.  
  
    4.  Legen Sie gegebenenfalls den Benutzernamen und das Kennwort für die ODBC\-Datenquelle fest.  Lassen Sie die Felder leer, falls die Datenquelle keinen Benutzernamen oder kein Kennwort erfordert.  
  
    5.  Geben Sie in die **SQL**\-Eigenschaft eine SQL\-Abfrage ein.  Die datengebundenen Steuerelemente sind in der Lage, eine Bindung mit den Ergebnissen der Abfrage herzustellen.  
  
5.  Legen Sie ggf. weitere Eigenschaften des RDO\-Remote\-Datensteuerelements fest.  
  
6.  Fügen Sie ein datengebundenes Steuerelement hinzu.  Fügen Sie z. B. das DBTabelle\-Steuerelement hinzu, und legen Sie die Datenquelle folgendermaßen fest:  
  
    1.  Klicken Sie mit der rechten Maustaste auf DBGrid, und klicken Sie dann auf **Eigenschaften**.  
  
    2.  Klicken Sie auf die Registerkarte **Alle**.  
  
    3.  Legen Sie die **DataSource**\-Eigenschaft als RDO\-Remote\-Datensteuerelement fest.  Klicken Sie auf das Dropdown\-Kombinationsfeld für die Eigenschaft, und suchen Sie die ID des RDO\-Remote\-Datensteuerelements.  Die Standard\-ID lautet IDC\_REMOTEDATACTL1.  
  
7.  Starten Sie den Testmodus durch Drücken von STRG\+T.  Sie können dann einen Bildlauf durch die Daten durchführen.  Sie beenden den Testmodus mit ESC oder durch Schließen des Dialogfelds.  
  
 Wenn Sie das Programm kompilieren und ausführen, sind Sie ebenfalls in der Lage, einen Bildlauf durch die Daten durchzuführen.  
  
## Siehe auch  
 [RDO\-Datenbindung](../../data/ado-rdo/rdo-databinding.md)   
 [Datenbindung mit ActiveX\-Steuerelementen in Visual C\+\+](../../data/ado-rdo/databinding-with-activex-controls-in-visual-cpp.md)