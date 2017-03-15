---
title: "Steuerelementtypen für die Symbolleiste | Microsoft-Dokumentation"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- ToolBar control styles
ms.assetid: 0f717eb9-fa32-4263-b852-809238863feb
caps.latest.revision: 16
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 1c50009a50c5b80e007add9de679315df6aecea9
ms.lasthandoff: 02/24/2017

---
# <a name="toolbar-control-styles"></a>Steuerelementtypen für die Symbolleiste
[CMFCToolBarButton-Klasse](../../mfc/reference/cmfctoolbarbutton-class.md) verfügt über eine Reihe von Style-Flags, die bestimmen, die Darstellung und Verhalten der Schaltfläche. Sie können eine Kombination dieser Flags festlegen, durch Aufrufen von [CMFCToolBarButton::SetStyle](../../mfc/reference/cmfctoolbarbutton-class.md#setstyle). Dieses Thema enthält die Style-Flagwerte und deren Bedeutung aufgeführt.  
  
## <a name="property-values"></a>Eigenschaftswerte  
 Die folgenden Werte bestimmen den Typ der Schaltfläche, die das Steuerelement darstellt:  
  
 TBBS_BUTTON  
 Standard Pushbutton (Standard).  
  
 TBBS_CHECKBOX  
 Das Kontrollkästchen.  
  
 TBBS_CHECKGROUP  
 Der Anfang einer Gruppe von Kontrollkästchen.  
  
 TBBS_GROUP  
 Der Anfang einer Gruppe von Optionsfeldern.  
  
 TBBS_SEPARATOR  
 Trennzeichen.  
  
 Die folgenden Werte stellen den aktuellen Status des Steuerelements dar:  
  
 TBBS_CHECKED  
 Das Kontrollkästchen ist aktiviert.  
  
 TBBS_DISABLED  
 Steuerelement ist deaktiviert.  
  
 TBBS_INDETERMINATE  
 Das Kontrollkästchen ist in einem unbestimmten Zustand.  
  
 TBBS_PRESSED  
 Gedrückt wird.  
  
 Der folgende Wert ändert das Layout der Schaltfläche in der Symbolleiste:  
  
 TBBS_BREAK  
 Platziert das Element in einer neuen Zeile oder in einer neuen Spalte ohne die Trennung von Spalten.  
  
## <a name="remarks"></a>Hinweise  
 Die aktuelle Formatvorlage befindet sich in [CMFCToolBarButton::m_nStyle](../../mfc/reference/cmfctoolbarbutton-class.md#m_nstyle). Legen Sie einen neuen Wert nicht in `m_nStyle` direkt, da einige abgeleiteten Klassen zusätzliche Verarbeitungsschritte beim Aufruf von `SetStyles`.  
  
 Visuelle Manager bestimmt die Darstellung der Schaltflächen in den einzelnen Zuständen. Finden Sie unter [Visualisierungs-Manager](../../mfc/visualization-manager.md) für Weitere Informationen.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxtoolbarbutton.h  
  
## <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)   
 [CMFCToolBarButton-Klasse](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [Visualisierungs-Manager](../../mfc/visualization-manager.md)



