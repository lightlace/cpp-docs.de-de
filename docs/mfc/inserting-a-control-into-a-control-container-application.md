---
title: "ActiveX-Steuerelementcontainer: Einf&#252;gen eines Steuerelements in eine Steuerelementcontainer-Anwendung"
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
  - "ActiveX-Steuerelementcontainer [C++], Einfügen von Steuerelementen"
  - "ActiveX-Steuerelemente [C++], Hinzufügen zu Projekten"
ms.assetid: bbb617ff-872f-43d8-b4d6-c49adb16b148
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# ActiveX-Steuerelementcontainer: Einf&#252;gen eines Steuerelements in eine Steuerelementcontainer-Anwendung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Bevor Sie auf ein ActiveX\-Steuerelement aus einer ActiveX\-Steuerelement\-Containeranwendung zugreifen können, müssen Sie das ActiveX\-Steuerelement der Containeranwendung mithilfe des Dialogfelds [ActiveX\-Steuerelement einfügen](../mfc/insert-activex-control-dialog-box.md) hinzufügen.  
  
 Um dem ActiveX\-Steuerelement\-Containerprojekt einem ActiveX\-Steuerelement hinzuzufügen, finden Sie unter [ActiveX\-Steuerelemente zu einem Dialogfeld anzeigen und hinzufügen](../mfc/viewing-and-adding-activex-controls-to-a-dialog-box.md).  
  
 Nachdem Sie das Steuerelement hinzufügen, müssen Sie eine Membervariable \(des ActiveX\-Steuerelement\-Typs\) der Dialogfeldklasse hinzufügen.  Weitere Informationen über diese Schritte, finden Sie unter [Hinzufügen einer Membervariablen](../ide/adding-a-member-variable-visual-cpp.md).  
  
 Sobald Sie die Membervariable hinzugefügt haben, wird eine Klasse, wird als eine Wrapperklasse, automatisch generiert und dem Projekt hinzugefügt.  Diese Klasse wird als Schnittstelle zwischen den Steuerelementcontainer und den eingebetteten Steuerelement verwendet.  
  
## Siehe auch  
 [ActiveX\-Steuerelementcontainer](../mfc/activex-control-containers.md)