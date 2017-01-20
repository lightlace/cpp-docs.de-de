---
title: "Verwenden von CSpinButtonCtrl"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "CSpinButtonCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSpinButtonCtrl-Klasse, Verwenden"
  - "Drehfeld-Steuerelement"
  - "Auf-Ab-Steuerelemente"
  - "Auf-Ab-Steuerelemente, Drehfeld-Steuerelement"
ms.assetid: a91db36b-e11e-42ef-8e89-51915cc486d2
caps.latest.revision: 14
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# Verwenden von CSpinButtonCtrl
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Das *Spinner\-Steuerelement* \(auch als *Auf\-Ab\-Steuerelement* \) stellt ein Paar auf Pfeile, die ein Benutzer klicken kann, um einen Wert anzupassen.  Dieser Wert ist die *aktuelle Position*.  Die Position bleibt innerhalb des Bereichs des Drehfelds.  Wenn der Benutzer auf den Aufwärtspfeil klickt, wird die Position zum Höchstwert; und der Benutzer auf den Abwärtspfeil klickt, wird die Position zum Minimum.  
  
 Das Spinner\-Steuerelement wird in MFC durch die [CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md)\-Klasse dargestellt.  
  
> [!NOTE]
>  Standardmäßig verfügt der Bereich für das Drehfeld das Maximum, das auf Null \(sind \(0\) sowie der Mindest\-, das bis 100 festgelegt ist.  Da der maximale Wert kleiner als der minimale Wert ist, auf den Aufwärtspfeil wird verringert die Position und Klicken auf den Abwärtspfeil erhöht sie.  Verwenden Sie [CSpinButtonCtrl::SetRange](../Topic/CSpinButtonCtrl::SetRange.md), diese Werte anzupassen.  
  
 Normalerweise wird die aktuelle Position in einem Begleitsteuerelement angezeigt.  Das Begleitsteuerelement wird als das *Buddyfenster*.  Eine Abbildung eines Drehfeld\-Steuerelements, finden Sie im [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)] unter [Übergreifend Auf\-Ab\-Steuerelemente](http://msdn.microsoft.com/library/windows/desktop/bb759889).  
  
 Ein Drehfeld\-Steuerelement und ein Bearbeitungssteuerelementbuddyfenster, Visual Studio zu erstellen, ziehen Sie zuerst ein Bearbeitungssteuerelement zum Dialogfeld oder das Fenster, und ziehen Sie dann ein Drehfeld\-Steuerelement.  Wählen Sie das Drehfeld\-Steuerelement aus und legen Sie dessen **Auto Buddy** und Eigenschaften **Set Buddy Integer** auf **True** fest.  Legen Sie die Eigenschaft **Ausrichtung** fest; **Rechts ausrichten** ist am häufigsten Arten.  Mit diesen Einstellungen wird das Bearbeitungssteuerelement als das Buddyfenster festgelegt, da es direkt das Bearbeitungssteuerelement in der Aktivierreihenfolge unmittelbar vorangestellt ist.  Die Bearbeitungssteuerelementanzeigenganzen zahlen und das Drehfeld\-Steuerelement wird in der rechten Seite des Bearbeitungssteuerelements eingebettet.  Optional können Sie den gültigen Bereich des Drehfeld\-Steuerelements festlegen, indem Sie die [CSpinButtonCtrl::SetRange](../Topic/CSpinButtonCtrl::SetRange.md)\-Methode.  Keine Ereignishandler sind erforderlich, zwischen dem Drehfeld\-Steuerelement und dem Buddyfenster kommuniziert da diese Daten direkt.  Wenn Sie ein Drehfeld\-Steuerelement zu einem anderen Zweck, beispielsweise, mithilfe einer Reihe von Fenstern zu blättern oder Dialogfelder verwenden, fügen Sie Handler für die `UDN_DELTAPOS` Meldung hinzu und führen Sie die benutzerdefinierte Aktion dort aus.  
  
## Worüber möchten Sie mehr erfahren?  
  
-   [Drehfeld\-Schaltflächenstile](../mfc/spin-button-styles.md)  
  
-   [Memberfunktionen für das Drehfeldsteuerelement](../mfc/spin-button-member-functions.md)  
  
## Siehe auch  
 [Steuerelemente](../mfc/controls-mfc.md)