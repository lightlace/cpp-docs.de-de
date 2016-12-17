---
title: "Dialogleisten"
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
  - "CDialogBar-Klasse, Dialogleisten"
  - "Steuerleisten, Dialogleisten"
  - "Dialogleisten"
  - "Dialogleisten, Informationen über Dialogleisten"
  - "MFC, Steuerleisten"
ms.assetid: 485c8055-6bb0-4051-8417-dd2971499321
caps.latest.revision: 11
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Dialogleisten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine Dialogleiste ist eine Symbolleiste, eine von [Symbolleisten](../mfc/control-bars.md), die beliebige Steuerelement enthalten kann.  Da sich Eigenschaften eines nicht modalen Dialogfelds ist, stellt ein [CDialogBar](../mfc/reference/cdialogbar-class.md)\-Objekt eine leistungsfähigere Symbolleiste.  
  
 Es gibt mehrere wesentliche Unterschiede zwischen einer Symbolleiste und ein `CDialogBar`\-Objekt.  Ein `CDialogBar`\-Objekt wird von einer Dialogfeldvorlagenressource erstellt, die Sie mit dem Visual C\+\+\-Dialog\-Editor erstellen können und die beliebige Windows\-Steuerelement enthalten kann.  Der Benutzer kann von Steuerelement zu Steuerelement mit der TAB\-TASTE.  Außerdem können Sie einem Ausrichtungsformat angeben, dass die Dialogleiste mit Teilen des übergeordneten Rahmenfensters ausrichten oder sogar sie gesorgt wird, wenn das übergeordnete Element vergrößert wird.  Die folgende Abbildung zeigt eine Dialogleiste mit einer Vielzahl von Steuerelementen an.  
  
 ![VC&#45;Dialogleiste](../mfc/media/vc378t1.png "vc378T1")  
Eine Dialogleiste  
  
 In anderen Hinsicht ist das Arbeiten mit einem `CDialogBar`\-Objekt wie die Arbeit mit einem nicht modalen Dialogfeld.  Verwenden Sie den Dialog\-Editor, um die Dialogfeldressource entwerfen und zu erstellen.  
  
 Einer der Vorzüge der Dialogleisten ist, dass sie andere Steuerelemente als Schaltflächen angeben können.  
  
 Während es üblich ist, eigene Dialogfeldklassen aus `CDialog` abzuleiten, leiten Sie normalerweise nicht die eigene Klasse für eine Dialogleiste.  Dialogleisten sind Erweiterungen zu einem Hauptfenster und alle Dialogleistensteuerelement\-benachrichtigungen, wie **BN\_CLICKED** oder **EN\_CHANGE**, werden übergeordnete Element der Dialogleiste, das Hauptfenster gesendet.  
  
## Siehe auch  
 [Benutzeroberflächenelemente](../mfc/user-interface-elements-mfc.md)   
 [Beispiel](../top/visual-cpp-samples.md)