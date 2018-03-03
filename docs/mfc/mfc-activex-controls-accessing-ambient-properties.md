---
title: 'MFC-ActiveX-Steuerelemente: Zugreifen auf Umgebungseigenschaften | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], accessing ambient properties
- properties [MFC], accessing ambient
ms.assetid: fdc9db29-e6b0-45d2-a879-8bd60e2058a7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b05e6d37a0550cf157dcd43a22689c9db029b51f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="mfc-activex-controls-accessing-ambient-properties"></a>MFC-ActiveX-Steuerelemente: Zugreifen auf Umgebungseigenschaften
In diesem Artikel wird erläutert, wie ein ActiveX-Steuerelement die Umgebungseigenschaften des Steuerelementcontainers zugreifen kann.  
  
 Ein Steuerelement erhalten Informationen zu den Container, durch Zugreifen auf Umgebungseigenschaften des Containers. Diese Eigenschaften machen die visuellen Merkmale, z. B. Background-Farbe für den Container, die aktuelle Schriftart, die vom Container und betriebsbereite Eigenschaften verwendet werden, z. B., ob der Container derzeit im Benutzermodus oder Designermodus ist verfügbar. Ein Steuerelement kann Umgebungseigenschaften verwenden, um anzupassen, sein Aussehen und Verhalten auf den bestimmten Container, in dem sie eingebettet ist. Ein Steuerelement sollte jedoch nie voraussetzen, ab seinem Container eine bestimmte Ambiente-Eigenschaft unterstützen. In der Tat können einige Container keine ambient Eigenschaften überhaupt unterstützt. In der ambient-Eigenschaft vorhanden ist sollte ein Steuerelement einen angemessener Standardwert voraussetzen.  
  
 Stellen Sie eine ambient-Eigenschaft für den Zugriff auf einen Aufruf von [COleControl:: GetAmbientProperty](../mfc/reference/colecontrol-class.md#getambientproperty). Diese Funktion erwartet die Dispatch-ID für die ambient-Eigenschaft als erster Parameter (in der Datei OLECTL. H definiert Dispatch-IDs für den Standardsatz von Ambiente-Eigenschaften).  
  
 Die Parameter von der `GetAmbientProperty` Funktion sind die Dispatch-ID, ein variant-Tag, der angibt, der erwartete Eigenschaftstyp und ein Zeiger auf Speicher, in dem der Wert zurückgegeben werden. Der Typ der Daten, die auf denen dieser Zeiger verweist variiert je nach den variant-Tag. Die Funktion gibt **"true"** der Container der Eigenschaft unterstützt, andernfalls wird zurückgegeben **"false"**.  
  
 Im folgenden Codebeispiel wird erhält den Wert der ambient-Eigenschaft namens "UserMode." Wenn die Eigenschaft nicht, von der Container den Standardwert unterstützt wird **"true"** wird davon ausgegangen, dass:  
  
 [!code-cpp[NVC_MFC_AxUI#30](../mfc/codesnippet/cpp/mfc-activex-controls-accessing-ambient-properties_1.cpp)]  
  
 Der Einfachheit halber `COleControl` Stellt Hilfsfunktionen, die Zugriff auf viele häufig verwendeten Umgebungseigenschaften und entsprechende Standardwerte zurückgeben, wenn die Eigenschaften nicht verfügbar sind. Diese Hilfsfunktionen lauten wie folgt:  
  
-   [COleControl::AmbientBackColor](../mfc/reference/colecontrol-class.md#ambientbackcolor)  
  
-   [AmbientDisplayName](../mfc/reference/colecontrol-class.md#ambientdisplayname)  
  
-   [AmbientFont](../mfc/reference/colecontrol-class.md#ambientfont)  
  
    > [!NOTE]
    >  Aufrufer muss Aufrufen **freigeben ()** der zurückgegebenen Schriftart.  
  
-   [AmbientForeColor](../mfc/reference/colecontrol-class.md#ambientforecolor)  
  
-   [AmbientLocaleID](../mfc/reference/colecontrol-class.md#ambientlocaleid)  
  
-   [AmbientScaleUnits](../mfc/reference/colecontrol-class.md#ambientscaleunits)  
  
-   [AmbientTextAlign](../mfc/reference/colecontrol-class.md#ambienttextalign)  
  
-   [AmbientUserMode](../mfc/reference/colecontrol-class.md#ambientusermode)  
  
-   [AmbientUIDead](../mfc/reference/colecontrol-class.md#ambientuidead)  
  
-   [AmbientShowHatching](../mfc/reference/colecontrol-class.md#ambientshowhatching)  
  
-   [AmbientShowGrabHandles](../mfc/reference/colecontrol-class.md#ambientshowgrabhandles)  
  
 Wenn der Wert der ambient-Eigenschaft (über eine Aktion des Containers) ändert die **OnAmbientPropertyChanged** Memberfunktion des Steuerelements aufgerufen. Überschreiben Sie diese Memberfunktion, um solche eine Benachrichtigung zu behandeln. Der Parameter für **OnAmbientPropertyChanged** ist die Dispatch-ID der betroffenen ambient-Eigenschaft. Der Wert dieser Dispatch-ID ist möglicherweise **u. DISPID_UNKNOWN lauten**, was bedeutet, dass eine oder mehrere Umgebungseigenschaften wurde geändert, aber Informationen darüber, welche Eigenschaften betroffen nicht verfügbar ist.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-ActiveX-Steuerelemente](../mfc/mfc-activex-controls.md)

