---
title: Grundleisten-Steuerelemente und Bänder | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- rebar controls [MFC], working with bands in
- bands, in rebar controls
ms.assetid: b647e7a5-9ea7-48b1-8e5f-096d104748f0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b1fac5f83f19fab37604a14e239cf505891c737f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33349850"
---
# <a name="rebar-controls-and-bands"></a>Grundleisten-Steuerelemente und Bänder
Der Hauptzweck eines Grundleisten-Steuerelements ist, fungiert als Container für untergeordnete Fenster, allgemeine Dialogfeldsteuerelemente, Menüs, Symbolleisten und So weiter. Diese Beschränkung wird durch das Konzept der "Band." unterstützt. Jedes Band Grundleisten kann eine beliebige Kombination von ziehelements-Leiste, eine Bitmap, einer textbezeichnung und ein untergeordnetes Fenster enthalten.  
  
 Klasse `CReBarCtrl` verfügt über viele Memberfunktionen, verwenden Sie zum Abrufen und Bearbeiten von Informationen für einen bestimmten Grundleisten-Band:  
  
-   [GetBandCount](../mfc/reference/crebarctrl-class.md#getbandcount) Ruft die Anzahl der aktuellen Bänder in die Grundleisten-Steuerelement ab.  
  
-   [GetBandInfo](../mfc/reference/crebarctrl-class.md#getbandinfo) initialisiert einen **REBARBANDINFO** Struktur mit Informationen aus dem angegebenen Band. Es wird ein entsprechendes [SetBandInfo](../mfc/reference/crebarctrl-class.md#setbandinfo) Memberfunktion.  
  
-   [GetRect](../mfc/reference/crebarctrl-class.md#getrect) Ruft das umschließende Rechteck des angegebenen Bandes.  
  
-   [GetRowCount](../mfc/reference/crebarctrl-class.md#getrowcount) Ruft die Anzahl der Band Zeilen in einem Grundleisten-Steuerelement ab.  
  
-   [IDToIndex](../mfc/reference/crebarctrl-class.md#idtoindex) Ruft den Index eines angegebenen Bandes ab.  
  
-   [GetBandBorders](../mfc/reference/crebarctrl-class.md#getbandborders) Ruft die Ränder eines Bandes ab.  
  
 Zusätzlich zur Manipulation sind mehrere Member-Funktionen bereitgestellt, die Sie für bestimmte rebarbereichen ausgeführt werden können.  
  
 [InsertBand](../mfc/reference/crebarctrl-class.md#insertband) und [DeleteBand](../mfc/reference/crebarctrl-class.md#deleteband) hinzufügen und Entfernen von rebarbereichen. [MinimizeBand](../mfc/reference/crebarctrl-class.md#minimizeband) und [MaximizeBand](../mfc/reference/crebarctrl-class.md#maximizeband) Auswirkungen auf die aktuelle Größe der einer bestimmten Grundleisten Band. [MoveBand](../mfc/reference/crebarctrl-class.md#moveband) ändert sich der Index eines bestimmten Grundleisten Bandes. [ShowBand](../mfc/reference/crebarctrl-class.md#showband) Blendet oder ein Band Grundleisten des Benutzers.  
  
 Das folgende Beispiel zeigt eine Symbolleistenband hinzufügen (`m_wndToolBar`) eines vorhandenen Grundleisten-Steuerelements (`m_wndReBar`). Das Band wird beschrieben, durch die Initialisierung der `rbi` Struktur und dem anschließenden Aufrufen der `InsertBand` Memberfunktion:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#27](../mfc/codesnippet/cpp/rebar-controls-and-bands_1.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CReBarCtrl](../mfc/using-crebarctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

