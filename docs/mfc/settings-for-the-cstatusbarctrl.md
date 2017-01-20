---
title: "Einstellungen f&#252;r CStatusBarCtrl"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "CStatusBarCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CStatusBarCtrl-Klasse, Einstellungen"
  - "Statusleiste-Steuerelement, Einstellungen"
ms.assetid: adeba0c3-17f3-435c-b140-a57845e9ce49
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Einstellungen f&#252;r CStatusBarCtrl
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Standardposition eines [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md) Statusfensters ist entlang dem unteren Rand des übergeordneten Fensters, Sie können jedoch dem Stil `CCS_TOP` angeben, damit es am oberen Rand des Clientbereichs des übergeordneten Fensters anzuzeigen.  
  
 Sie können den **SBARS\_SIZEGRIP** Format angeben, um ein Ende des Größenziehpunkts des `CStatusBarCtrl` Statusfensters rechts einzuschließen.  Ein Größenziehpunkt entspricht einem Größenanpassungsrahmen ähnlich; es ist ein rechteckiger Bereich, den der Benutzer klicken und ziehen kann, um das übergeordnete Fenster Größe zu ändern.  
  
> [!NOTE]
>  Wenn Sie `CCS_TOP` kombinieren und **SBARS\_SIZEGRIP** formatiert, ist der daraufhin Größenziehpunkt nicht aktiviert, obwohl das System ihn im Statusfenster zeichnet.  
  
 Die Fensterprozedur zum Statusfenster wird automatisch der Ausgangsgröße und die Position des Steuerfensters fest.  Die Breite ist die selbe wie die des Clientbereichs des übergeordneten Fensters.  Die Höhe basiert auf die Metriken der Schriftart, die derzeit in den Gerätekontext des Statusfensters und der Breite des Rahmens des Fensters aktiviert ist.  
  
 Die Fensterprozedur angepasst automatisch die Größe des Statusfensters, wenn sie `WM_SIZE` eine Meldung empfängt.  Normalerweise wenn die Größe des übergeordneten Fensters ändert, sendet das übergeordnete Element `WM_SIZE` eine Meldung im Statusfenster.  
  
 Sie können die Mindesthöhe Zeichnungsbereich eines Statusfensters festlegen, indem Sie [SetMinHeight](../Topic/CStatusBarCtrl::SetMinHeight.md) aufrufen und die minimale Höhe in Pixel angeben.  Der Zeichnungsbereich enthält nicht den Rahmen des Fensters.  
  
 Sie rufen die Breite der Kontext eines Statusfensters ab, indem Sie [GetBorders](../Topic/CStatusBarCtrl::GetBorders.md) aufrufen.  Diese Memberfunktion enthält den Zeiger auf einen DreiElementarray, dass die Breite eines horizontalen Bereichs, des vertikalen Rahmens und des Rahmens zwischen Rechtecken empfängt.  
  
## Siehe auch  
 [Verwenden von CStatusBarCtrl](../mfc/using-cstatusbarctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)