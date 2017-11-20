---
title: Ableiten von Steuerelementen von einem Standardsteuerelement | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- standard controls [MFC], deriving controls from
- common controls [MFC], deriving from
- derived controls
- controls [MFC], derived
- Windows common controls [MFC], deriving from
- standard controls
ms.assetid: a6f84315-7007-4e0e-8576-78be81254802
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 73370659d07e38565cc3e9b4cf349a0328b921b8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="deriving-controls-from-a-standard-control"></a>Ableiten von Steuerelementen von einem Standardsteuerelement
Wie jede [CWnd](../mfc/reference/cwnd-class.md)-abgeleitete Klasse, Sie können Verhalten eines Steuerelements ändern, indem das Ableiten einer neuen Klasse aus einer vorhandenen Steuerelementklasse.  
  
### <a name="to-create-a-derived-control-class"></a>So erstellen Sie eine abgeleitetes Steuerelement-Klasse  
  
1.  Leiten Sie eine Klasse aus einer vorhandenen Steuerelementklasse, und überschreiben Sie optional die **erstellen** -Memberfunktion aufrufen, damit die erforderlichen Argumente für die Basisklasse bereitgestellt **erstellen** Funktion.  
  
2.  Geben Sie Meldungshandler Memberfunktionen und Meldungszuordnungseinträge so ändern Sie das Verhalten des Steuerelements in Reaktion auf bestimmte Windows-Meldungen. Finden Sie unter [Zuordnen von Meldungen zu Funktionen](../mfc/reference/mapping-messages-to-functions.md).  
  
3.  Geben Sie neue Memberfunktionen, um die Funktionalität des Steuerelements (optional) erweitern.  
  
 Verwenden eines abgeleiteten Steuerelements in einem Dialogfeld ist zusätzliche Arbeit erforderlich. Die Typen und Positionen der Steuerelemente in einem Dialogfeld werden normalerweise in einer Dialogfeldvorlagen-Ressource angegeben. Wenn Sie eine abgeleitete Klasse zu erstellen können Sie es in einer Dialogfeldvorlage angeben, da der Ressourcencompiler keinerlei wissen über die abgeleitete Klasse kennt.  
  
#### <a name="to-place-your-derived-control-in-a-dialog-box"></a>Zum Platzieren von Ihr abgeleiteten Steuerelements in einem Dialogfeld  
  
1.  Betten Sie ein Objekt der abgeleiteten Steuerelementklasse in der Deklaration der abgeleiteten Dialogfeldklasse.  
  
2.  Überschreiben der `OnInitDialog` Memberfunktion in eigener Dialogfeldklassen zum Aufrufen der `SubclassDlgItem` Memberfunktion für die abgeleitete Steuerelement.  
  
 `SubclassDlgItem`"dynamisch Unterklassen" erstellt ein Steuerelement aus einer Dialogfeldvorlage. Wenn ein Steuerelement dynamisch als Unterklasse definiert ist, Sie verknüpfen in Windows, einige Nachrichten innerhalb Ihrer eigenen Anwendung verarbeitet werden und dann die verbleibenden Nachrichten an Windows übergeben. Weitere Informationen finden Sie unter der [SubclassDlgItem](../mfc/reference/cwnd-class.md#subclassdlgitem) Memberfunktion der Klasse `CWnd` in der *MFC-Referenz*. Das folgende Beispiel zeigt, wie Sie eine Überschreibung der schreiben `OnInitDialog` Aufrufen `SubclassDlgItem`:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#3](../mfc/codesnippet/cpp/deriving-controls-from-a-standard-control_1.cpp)]  
  
 Da in der Dialogfeldklasse abgeleitete Steuerelement eingebettet ist, wird er erstellt werden, wenn das Dialogfeld wird erstellt, und es werden zerstört, wenn das Dialogfeld zerstört wird. Vergleichen Sie diesen Code im Beispiel in [Hinzufügen von Steuerelementen By Hand](../mfc/adding-controls-by-hand.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen und Verwenden von Steuerelementen](../mfc/making-and-using-controls.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

