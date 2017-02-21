---
title: "Festlegen von Steuerelementeigenschaften zur Entwurfszeit | Microsoft Docs"
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
  - "ActiveX-Steuerelemente [C++], Eigenschaften"
ms.assetid: 963bf498-d371-4cfd-8bed-865427dcfad9
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Festlegen von Steuerelementeigenschaften zur Entwurfszeit
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Eigenschaften von Steuerelementen lassen sich zur Entwurfszeit über den Dialog\-Editor festlegen.  Beim Festlegen einer Eigenschaft wird das Steuerelement vom Ressourcen\-Editor mit dem angegebenen Wert initialisiert.  Die Eigenschaft kann weiterhin programmgesteuert geändert werden.  
  
 Mithilfe der in allen [datengebundenen Steuerelementen](../../data/ado-rdo/databinding-with-activex-controls-in-visual-cpp.md) enthaltenen **DataSource**\-Eigenschaft können Sie das [Datenquelle](../../data/ado-rdo/databinding-with-activex-controls-in-visual-cpp.md)\-Steuerelement für die Bindung angeben.  
  
 Wenn Sie ein einfaches, an ADO\-Daten gebundenes Steuerelement an ein ADO\-Datensteuerelement \(ADODC\) binden, müssen Sie das Steuerelement einer Spalte zuordnen, indem Sie die **DataField**\-Eigenschaft auf ein gültiges Feld im Rowset festlegen.  Andernfalls wird die kompilierte Anwendung in einem laufenden Debugbuild bestätigt \(die Assertion weist lediglich darauf hin, dass das Steuerelement an eine NULL\-Spalte gebunden wurde\).  
  
> [!NOTE]
>  Auf der Eigenschaftenregisterkarte **Allgemein** können Sie eine Steuerelement\-ID und weitere für die RC\-Datei erforderliche Eigenschaften festlegen. \(Die RC\-Datei wird später kompiliert, um den Ressourcencode für ein Windows\-Programm zu generieren.\)  
  
### So legen Sie eine Eigenschaft auf der Registerkarte Alle fest  
  
1.  [Fügen Sie ein ActiveX\-Steuerelement](../../data/ado-rdo/inserting-the-control-into-a-visual-cpp-application.md) in ein Dialogfeld ein.  
  
2.  Klicken Sie im Dialog\-Editor mit der rechten Maustaste auf das Steuerelement, und klicken Sie dann auf **Eigenschaften**.  
  
3.  Klicken Sie auf die Registerkarte **Alle**, um die Steuerelementeigenschaften anzuzeigen.  Geben Sie bei einer bestehenden Eigenschaft den Initialisierungswert ein.  
  
 Informationen zum Festlegen von Steuerelementeigenschaften zur Laufzeit finden Sie unter [Ändern des Laufzeitverhaltens eines Steuerelements](../../data/ado-rdo/modifying-a-control-s-run-time-behavior.md).  
  
## Siehe auch  
 [Verwenden von ActiveX\-Steuerelementen](../../data/ado-rdo/using-activex-controls.md)