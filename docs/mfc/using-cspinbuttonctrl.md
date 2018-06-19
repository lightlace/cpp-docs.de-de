---
title: Verwenden von CSpinButtonCtrl | Microsoft Docs
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
ms.openlocfilehash: 03b1e83977c1d75070e8878dfdcc53c7afca7a86
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33384399"
---
# <a name="using-cspinbuttonctrl"></a>Verwenden von CSpinButtonCtrl
Die *Drehfeld* Control (auch bekannt als ein *nach oben und unten* Steuerelement) stellt einem pfeilepaar zusammenlaufen, die ein Benutzer klicken kann, um einen Wert anzupassen. Dieser Wert wird als bezeichnet den *aktuelle Position*. Die Position, die innerhalb des Bereichs von dem Drehfeld bleibt bestehen. Klickt der Benutzer auf den Pfeil nach oben, verschiebt die Position für die maximale Anzahl; und klickt der Benutzer auf den Pfeil nach unten, verschiebt die Position in Richtung der Mindestwert.  
  
 Das Drehfeld-Steuerelement wird in MFC von dargestellt die [CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md) Klasse.  
  
> [!NOTE]
>  Standardmäßig hat der Bereich für das Drehfeld das Maximum auf 0 (null) und das Minimum auf 100 festgelegt. Da der maximale Wert kleiner als der minimale Wert ist, wird auf den Pfeil nach oben die Position verringert, und klicken auf den Pfeil nach unten erhöht. Verwendung [CSpinButtonCtrl:: SetRange](../mfc/reference/cspinbuttonctrl-class.md#setrange) diese Werte anpassen.  
  
 In der Regel wird die aktuelle Position in einem Begleit-Steuerelement angezeigt. Das Begleit-Steuerelement heißt die *Buddy-Fenster*. Eine Abbildung ein Drehfeldsteuerelement, finden Sie unter [zu auf-ab-Steuerelemente](http://msdn.microsoft.com/library/windows/desktop/bb759889) im Windows SDK.  
  
 Um ein Drehfeld-Steuerelement und Steuerelementfensters Buddy eine Bearbeiten in Visual Studio zu erstellen, ziehen Sie zuerst ein Bearbeitungssteuerelement zum Dialogfeld oder Fenster, und ziehen Sie dann ein Drehfeld-Steuerelement. Wählen Sie das Drehfeld-Steuerelement, und legen seine **Auto-Buddy** und **Buddy-Integer festgelegt** Eigenschaften **"true"**. Legen Sie auch die **Ausrichtung** Eigenschaft ein. **Rechtsbündig** liegt meist daran ist. Mit diesen Einstellungen wird das Bearbeitungssteuerelement als Buddy-Fensters festgelegt, weil er direkt das Bearbeitungssteuerelement in der Aktivierreihenfolge vorangestellt. Das Bearbeitungssteuerelement Zeigt ganze Zahlen, und das Drehfeld-Steuerelement auf der rechten Seite des Bearbeitungssteuerelements eingebettet ist. Sie können optional, den gültigen Bereich für das Drehfeld-Steuerelement festlegen, mit der [CSpinButtonCtrl:: SetRange](../mfc/reference/cspinbuttonctrl-class.md#setrange) Methode. Keine Ereignishandler sind erforderlich, für die Kommunikation zwischen den Drehfeld-Steuerelement und Buddy-Fenster, da sie Daten direkt austauschen. Wenn Sie ein Drehfeld-Steuerelement zu einem anderen Zweck verwenden, z. B. um einen Bildlauf durch eine Sequenz von Windows oder Dialogfeldern, klicken Sie dann hinzufügen einen Handler für das `UDN_DELTAPOS` Meldungen, und führen Sie die benutzerdefinierte Aktion vorhanden.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren  
  
-   [Drehfeld-Schaltflächenstile](../mfc/spin-button-styles.md)  
  
-   [Memberfunktionen für das Drehfeldsteuerelement](../mfc/spin-button-member-functions.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Steuerelemente](../mfc/controls-mfc.md)

