---
title: Verwenden von CSpinButtonCtrl | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CSpinButtonCtrl
dev_langs:
- C++
helpviewer_keywords:
- up-down controls [MFC], spin button control
- up-down controls
- spin button control
- CSpinButtonCtrl class [MFC], using
ms.assetid: a91db36b-e11e-42ef-8e89-51915cc486d2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3768cda94eb0adda8562c46124be8e9b2d4a2501
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43215091"
---
# <a name="using-cspinbuttonctrl"></a>Verwenden von CSpinButtonCtrl
Die *Drehfeld* Control (auch bekannt als ein *nach oben und unten* Steuerelement) bietet von einem Paar Pfeilen, die ein Benutzer klicken kann, um einen Wert anzupassen. Dieser Wert wird als bezeichnet die *aktuelle Position*. Die Position bleibt innerhalb des Bereichs von der Schaltfläche "starten". Klickt der Benutzer auf den Pfeil nach oben, verschiebt die Position, für die maximale Anzahl; und klickt der Benutzer auf den Pfeil nach unten, verschiebt die Position in Richtung Minimum.  
  
 Das Drehfeld-Steuerelement wird in MFC nach dargestellt die [CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md) Klasse.  
  
> [!NOTE]
>  Standardmäßig verfügt über der Bereich für die Schaltfläche "starten", das Maximum auf 0 (null) und das Minimum auf 100 festgelegt. Da der maximale Wert kleiner als der minimale Wert ist, wird auf den Pfeil nach oben die Position verringert, und klicken Sie auf den Pfeil nach unten wird vergrößert. Verwendung [CSpinButtonCtrl:: SetRange](../mfc/reference/cspinbuttonctrl-class.md#setrange) zum Anpassen dieser Werte.  
  
 In der Regel wird die aktuelle Position in einem weiteren Steuerelement angezeigt. Das zugehörige Steuerelement heißt die *Buddy-Fenster*. Eine Abbildung ein Drehfeld-Steuerelement, finden Sie unter [-ab-Steuerelemente](/windows/desktop/Controls/up-down-controls) im Windows SDK.  
  
 Um ein Drehfeld-Steuerelement und eine Bearbeiten-Steuerelement Buddy-Fenster in Visual Studio zu erstellen, ziehen Sie zuerst ein Bearbeitungssteuerelement zum Dialogfeld oder Fenster, und ziehen Sie dann ein Drehfeld-Steuerelement. Wählen Sie das Drehfeld-Steuerelement, und legen Sie dessen **Auto Buddy** und **Buddy Integer festgelegt** Eigenschaften **"true"**. Legen Sie auch die **Ausrichtung** Eigenschaft **Rechts auszurichten** häufigste ist. Mit diesen Einstellungen wird das Steuerelement zum Bearbeiten als das Buddyfenster festgelegt, da sie direkt das Bearbeitungssteuerelement in der Aktivierreihenfolge vorangestellt ist. Das Bearbeitungssteuerelement Zeigt ganze Zahlen ein, und das Drehfeld-Steuerelement in der rechten Seite des Bearbeitungssteuerelements eingebettet ist. Optional können Sie mithilfe des gültigen Bereichs des Drehfeld-Steuerelements festlegen der [CSpinButtonCtrl:: SetRange](../mfc/reference/cspinbuttonctrl-class.md#setrange) Methode. Keine Ereignishandler sind erforderlich, zwischen dem Drehfeld-Steuerelement und Buddy-Fenster zu kommunizieren, da sie Daten direkt austauschen. Wenn Sie ein Drehfeld-Steuerelement zu einem anderen Zweck verwenden, z. B. um die Seite werden eine Sequenz von Fenster oder Dialogfelder, fügen Sie dann einen Handler für die Nachricht UDN_DELTAPOS hinzu und führen Sie gibt es für Ihre benutzerdefinierte Aktion aus.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren  
  
-   [Drehfeld-Schaltflächenstile](../mfc/spin-button-styles.md)  
  
-   [Memberfunktionen für das Drehfeldsteuerelement](../mfc/spin-button-member-functions.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Steuerelemente](../mfc/controls-mfc.md)

