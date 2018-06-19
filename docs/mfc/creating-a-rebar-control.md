---
title: Erstellen eines Grundleisten-Steuerelements | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- rebar controls [MFC], creating
- CReBarCtrl class [MFC], creating
ms.assetid: 0a012e08-772b-4f6a-af86-7cb651d11d3e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1deb33adc104775cf9b76daf75d4ee08b6475f0a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33342306"
---
# <a name="creating-a-rebar-control"></a>Erstellen eines Grundleisten-Steuerelements
[CReBarCtrl](../mfc/reference/crebarctrl-class.md) Objekte erstellt werden soll, bevor das übergeordnete Objekt sichtbar ist. Dadurch wird die Möglichkeiten von Darstellungsprobleme minimiert.  
  
 Beispielsweise werden Rebar-Steuerelemente (verwendet in Frame Fensterobjekten) häufig als übergeordnete Fenster für Symbolleisten-Steuerelemente verwendet. Daher ist das übergeordnete Element eines Grundleisten-Steuerelement die Frame-Fensterobjekt. Da die Frame-Fensterobjekt das übergeordnete Element ist die `OnCreate` Memberfunktion (des übergeordneten Elements) ist eine ausgezeichnete Möglichkeit, Grundleisten-Steuerelement zu erstellen.  
  
 Verwenden einer `CReBarCtrl` -Objekt, Sie werden in der Regel gehen Sie folgendermaßen vor:  
  
### <a name="to-use-a-crebarctrl-object"></a>Ein Objekt CReBarCtrl verwendet  
  
1.  Erstellen der [CReBarCtrl](../mfc/reference/crebarctrl-class.md) Objekt.  
  
2.  Rufen Sie [erstellen](../mfc/reference/crebarctrl-class.md#create) zum Erstellen von allgemeinen Windows Grundleisten-Steuerelements und fügen Sie es auf die `CReBarCtrl` -Objekt, wobei alle gewünschten Formatvorlagen.  
  
3.  Laden Sie eine Bitmap mit einem Aufruf von [LoadBitmap](../mfc/reference/cbitmap-class.md#loadbitmap), wie der Hintergrund des Grundleisten-Steuerelements verwendet werden.  
  
4.  Erstellen Sie und initialisieren Sie alle untergeordneten Fensterobjekte (Symbolleisten, Dialogfeld-Steuerelemente und So weiter), die vom Objekt Grundleisten-Steuerelement enthalten sein werden.  
  
5.  Initialisieren einer **REBARBANDINFO** Struktur mit den erforderlichen Informationen für das Band eingefügt wird.  
  
6.  Rufen Sie [InsertBand](../mfc/reference/crebarctrl-class.md#insertband) vorhandene untergeordnete Fenster eingefügt (z. B. `m_wndReToolBar`) in das neue Grundleistensteuerelement. Weitere Informationen zum Einfügen von Bändern in ein vorhandenes Grundleistensteuerelement, finden Sie unter [Rebar-Steuerelemente und Bänder](../mfc/rebar-controls-and-bands.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CReBarCtrl](../mfc/using-crebarctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

