---
title: "ATL-Dialogfeld-Assistent | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "vc.codewiz.class.atl.dlg.overview"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL-Dialogfeld-Assistent"
  - "ATL-Projekte, Hinzufügen von Dialogressourcen"
ms.assetid: b0b9ace5-83c9-40d3-82c3-eb6293f10583
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# ATL-Dialogfeld-Assistent
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Mit diesem Assistenten wird ein von [CAxDialogImpl](../../atl/reference/caxdialogimpl-class.md) abgeleitetes ATL\-Dialogfeldobjekt in das Projekt eingefügt.  Ein von `CAxDialogImpl` abgeleitetes Dialogfeld kann ActiveX\-Steuerelemente aufnehmen.  
  
 Der Assistent erstellt eine Dialogressource mit den Standardschaltflächen **OK** und **Abbrechen**.  In der Ressourcenansicht des [Dialog\-Editors](../../mfc/dialog-editor.md) können Sie die Dialogressource bearbeiten und ActiveX\-Steuerelemente hinzufügen.  
  
 Der Assistent fügt eine [Meldungszuordnung](../../atl/message-maps-atl.md) und Deklarationen für die Behandlung standardmäßiger Click\-Ereignisse in die Headerdatei ein.  Weitere Informationen über ATL\-Dialogfelder finden Sie unter [Implementieren eines Dialogfelds](../../atl/implementing-a-dialog-box.md).  
  
 **Kurzer Name**  
 Legt den abgekürzten Namen für das ATL\-Dialogfeldobjekt fest.  Sofern Sie die Felder nicht einzeln ändern, bestimmt der hier angegebene Name den Klassennamen und die Dateinamen \(**.cpp** und **.h**\).  
  
 `Class`  
 Legt den Namen der zu erstellenden Klasse fest.  Dieser Name basiert auf dem unter **Kurzer Name** angegebenen Namen. Allerdings wird der Buchstabe C als typisches Präfix für einen Klassennamen vorangestellt.  
  
 **.h\-Datei**  
 Legt den Namen der Headerdatei für die neue Objektklasse fest.  Dieser Name basiert standardmäßig auf dem unter **Kurzer Name** angegebenen Namen.  Klicken Sie auf die Schaltfläche mit den Auslassungspunkten \(...\), um den Dateinamen am gewünschten Speicherort zu speichern oder um die Klassendeklaration an eine vorhandene Datei anzufügen.  Wenn Sie eine vorhandene Datei auswählen, wird sie vom Assistenten erst am ausgewählten Speicherort gespeichert, nachdem Sie im Assistenten auf **Fertig stellen** geklickt haben.  
  
 Der Assistent ist nicht in der Lage, Dateien zu überschreiben.  Wenn Sie den Namen einer vorhandenen Datei auswählen und dann auf **Fertig stellen** klicken, wird vom Assistenten eine Bestätigung angefordert, die Klassendeklaration an den Inhalt der Datei anzufügen.  Klicken Sie auf **Ja**, um die Datei anzufügen, und klicken Sie auf **Nein**, um zum Assistenten zurückzukehren und einen anderen Dateinamen anzugeben.  
  
 **.cpp\-Datei**  
 Legt für die neue Objektklasse den Namen der Implementierungsdatei fest.  Dieser Name basiert standardmäßig auf dem unter **Kurzer Name** angegebenen Namen.  Klicken Sie auf die Schaltfläche mit den Auslassungspunkten \(...\), um den Dateinamen am gewünschten Speicherort zu speichern.  Die Datei wird erst am ausgewählten Speicherort gespeichert, wenn Sie im Assistenten auf **Fertig stellen** klicken.  
  
 Der Assistent ist nicht in der Lage, Dateien zu überschreiben.  Wenn Sie den Namen einer vorhandenen Datei auswählen und dann auf **Fertig stellen** klicken, werden Sie vom Assistenten gefragt, ob die Klassenimplementierung an den Inhalt der Datei angefügt werden soll.  Klicken Sie auf **Ja**, um die Datei anzufügen, und klicken Sie auf **Nein**, um zum Assistenten zurückzukehren und einen anderen Dateinamen anzugeben.  
  
## Siehe auch  
 [ATL Dialog Box](../../atl/reference/adding-an-atl-dialog-box.md)