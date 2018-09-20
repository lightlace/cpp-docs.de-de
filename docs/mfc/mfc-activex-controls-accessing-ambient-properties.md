---
title: 'MFC-ActiveX-Steuerelemente: Zugreifen auf Umgebungseigenschaften | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], accessing ambient properties
- properties [MFC], accessing ambient
ms.assetid: fdc9db29-e6b0-45d2-a879-8bd60e2058a7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8aaa379513695f3cd39589a1009e3a157d957761
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46407900"
---
# <a name="mfc-activex-controls-accessing-ambient-properties"></a>MFC-ActiveX-Steuerelemente: Zugreifen auf Umgebungseigenschaften

In diesem Artikel wird erläutert, wie ein ActiveX-Steuerelement die ambient-Eigenschaften des zugehörigen Steuerelementcontainers zugreifen kann.

Ein Steuerelement kann Informationen zu den Container zugreifen auf Umgebungseigenschaften des Containers abrufen. Diese Eigenschaften machen die visuellen Merkmale, z. B. die Hintergrundfarbe des Containers der aktuellen Schriftart, die durch den Container und die betriebsbereite Eigenschaften verwendet werden, z. B., ob der Container derzeit im Benutzermodus oder Designer-Modus ist verfügbar. Ein Steuerelement kann Umgebungseigenschaften verwenden, um anzupassen, dessen Darstellung und Verhalten auf den bestimmten Container, die in dem sie eingebettet ist. Allerdings sollte ein Steuerelement niemals davon ausgegangen, dass der Container bestimmte Ambiente-Eigenschaft unterstützt. In der Tat einige Container unterstützen möglicherweise keine Umgebungseigenschaften überhaupt. In der ambient-Eigenschaft vorhanden ist sollte ein Steuerelement einen angemessener Standardwert voraussetzen.

Stellen Sie für den Zugriff auf ambient-Eigenschaft, die einen Aufruf von [COleControl:: GetAmbientProperty](../mfc/reference/colecontrol-class.md#getambientproperty). Diese Funktion erwartet, dass die Dispatch-ID für die ambient-Eigenschaft als ersten Parameter (in der Datei OLECTL. H definiert die Dispatch-IDs für den standardmäßigen Satz von ambient-Eigenschaften).

Die Parameter der `GetAmbientProperty` Funktion gibt die Dispatch-ID, ein variant-Tag, der angibt, der erwartete Eigenschaftstyp und einen Zeiger auf den Speicher, in denen der Wert zurückgegeben werden soll. Der Typ der Daten, die auf denen this-Zeiger verweist, hängt das variant-Tag ab. Die Funktion gibt **"true"** , wenn der Container der Eigenschaft unterstützt wird, andernfalls **"false"**.

Im folgenden Codebeispiel ruft den Wert der ambient-Eigenschaft namens "UserMode." Wenn die Eigenschaft nicht, durch den Container, den Standardwert unterstützt wird **"true"** wird davon ausgegangen, dass:

[!code-cpp[NVC_MFC_AxUI#30](../mfc/codesnippet/cpp/mfc-activex-controls-accessing-ambient-properties_1.cpp)]

Der Einfachheit halber `COleControl` Stellt Hilfsfunktionen, die Zugriff auf viele häufig verwendeten Umgebungseigenschaften und entsprechende Standardwerte zurück, wenn die Eigenschaften nicht verfügbar sind. Diese Hilfsfunktionen lauten wie folgt aus:

- [COleControl::AmbientBackColor](../mfc/reference/colecontrol-class.md#ambientbackcolor)

- [AmbientDisplayName](../mfc/reference/colecontrol-class.md#ambientdisplayname)

- [AmbientFont](../mfc/reference/colecontrol-class.md#ambientfont)

    > [!NOTE]
    >  Aufrufer muss Aufrufen `Release( )` für die zurückgegebene Schriftart.

- [AmbientForeColor](../mfc/reference/colecontrol-class.md#ambientforecolor)

- [AmbientLocaleID](../mfc/reference/colecontrol-class.md#ambientlocaleid)

- [AmbientScaleUnits](../mfc/reference/colecontrol-class.md#ambientscaleunits)

- [AmbientTextAlign](../mfc/reference/colecontrol-class.md#ambienttextalign)

- [AmbientUserMode](../mfc/reference/colecontrol-class.md#ambientusermode)

- [AmbientUIDead](../mfc/reference/colecontrol-class.md#ambientuidead)

- [AmbientShowHatching](../mfc/reference/colecontrol-class.md#ambientshowhatching)

- [AmbientShowGrabHandles](../mfc/reference/colecontrol-class.md#ambientshowgrabhandles)

Wenn der Wert der ambient-Eigenschaft (über eine Aktion des Containers), ändert der `OnAmbientPropertyChanged` Memberfunktion des Steuerelements aufgerufen wird. Überschreiben Sie diese Memberfunktion, um eine solche Benachrichtigung zu verarbeiten. Der Parameter für `OnAmbientPropertyChanged` ist die Dispatch-ID der betroffenen ambient-Eigenschaft. Der Wert dieser Dispatch-ID handelt es sich möglicherweise um DISPID_UNKNOWN, der angibt, dass mindestens eine Ambiente-Eigenschaften wurde geändert, aber Informationen darüber, welche Eigenschaften betroffen sind, ist nicht verfügbar.

## <a name="see-also"></a>Siehe auch

[MFC-ActiveX-Steuerelemente](../mfc/mfc-activex-controls.md)

