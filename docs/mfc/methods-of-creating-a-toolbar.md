---
title: Methoden zum Erstellen einer Symbolleiste | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CToolBarCtrl class [MFC], and CToolBar class [MFC]
- CToolBar class [MFC], creating toolbars
- MFC toolbars
- toolbar controls [MFC]
- toolbar controls [MFC], creating
- CToolBarCtrl class [MFC], creating toolbars
ms.assetid: f19d8d65-d49f-445c-abe8-d47d3e4101c8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 052f1578386746f9a4d9892576f09b3b61547289
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="methods-of-creating-a-toolbar"></a>Methoden zum Erstellen einer Symbolleiste
MFC stellt zwei Klassen zum Erstellen von Symbolleisten: [CToolBar](../mfc/reference/ctoolbar-class.md) und [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) (die dient als Wrapper für die allgemeine Windows-Steuerungs-API). `CToolBar` Stellt die Funktionalität des allgemeinen Symbolleisten-Steuerelements, und viele der erforderlichen steuerelementeinstellungen für allgemeine und Strukturen verarbeitet. die resultierende ausführbare Datei in der Regel werden jedoch größer ist als mit erstellt `CToolBarCtrl`.  
  
 `CToolBarCtrl` in der Regel die Ergebnisse in eine kleinere ausführbare Datei, und Sie bevorzugen `CToolBarCtrl` , wenn Sie nicht beabsichtigen, auf die Symbolleiste in der MFC-Architektur integriert. Wenn Sie planen, verwenden Sie `CToolBarCtrl` und die Symbolleiste in der MFC-Architektur integriert, Sie müssen zusätzliche Sorgfalt MFC-Symbolleisten-Steuerelement Manipulationen zu kommunizieren. Diese Kommunikation ist nicht schwierig. Es ist jedoch zusätzliche Arbeit, die nicht benötigten ist bei Verwendung von `CToolBar`.  
  
 Visual C++ bietet zwei Möglichkeiten, die allgemeine Symbolleisten-Steuerelement nutzen.  
  
-   Erstellen Sie die Symbolleiste mit `CToolBar`, und rufen dann [GetToolBarCtrl](../mfc/reference/ctoolbar-class.md#gettoolbarctrl) für den Zugriff auf die `CToolBarCtrl` Memberfunktionen.  
  
-   Erstellen Sie die Symbolleiste mit [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)Konstruktor.  
  
 Beide Methoden erhalten Sie Zugriff auf die Memberfunktionen des Symbolleisten-Steuerelements. Beim Aufruf `CToolBar::GetToolBarCtrl`, es gibt einen Verweis auf ein `CToolBarCtrl` Objekt, damit die beiden Satz von Memberfunktionen verwendet werden kann. Finden Sie unter [CToolBar](../mfc/reference/ctoolbar-class.md) Informationen zum Erstellen und zum Erstellen einer Symbolleiste mit `CToolBar`.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CToolBarCtrl](../mfc/using-ctoolbarctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

