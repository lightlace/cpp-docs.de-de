---
title: 'MFC-ActiveX-Steuerelemente: Hinzufügen von benutzerdefinierten Methoden | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 09/12/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], methods
- PtInCircle custom method [MFC]
ms.assetid: 8f8dc344-44a0-4021-8db5-4cdd3d700e18
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 428f43d5cd1a0cfaa4b5f829b59208ce96eab85d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46441082"
---
# <a name="mfc-activex-controls-adding-custom-methods"></a>MFC-ActiveX-Steuerelemente: Hinzufügen von benutzerdefinierten Methoden

Benutzerdefinierte Methoden unterscheiden sich von vordefinierten Methoden, da sie nicht bereits durch implementiert sind `COleControl`. Sie müssen die Implementierung für jede benutzerdefinierte Methode angeben, die Sie zu Ihrem Steuerelement hinzuzufügen.

>[!IMPORTANT]
> ActiveX ist eine veraltete Technologie, die nicht für Neuentwicklungen verwendet werden soll. Weitere Informationen über moderne Technologien, die ActiveX Ersetzen eines finden Sie unter [ActiveX-Steuerelemente](activex-controls.md).

Ein ActiveX-Steuerelement-Benutzer kann eine benutzerdefinierte Methode zu einem beliebigen Zeitpunkt für das Steuerelement spezifische Aktionen aufrufen. Die Dispatch-Eintrag für die Zuordnung für benutzerdefinierte Methoden ist das DISP_FUNCTION.

##  <a name="_core_adding_a_custom_method_with_classwizard"></a> Hinzufügen einer benutzerdefinierten Methode mit dem Assistenten hinzufügen

Das folgende Verfahren veranschaulicht die benutzerdefinierte Methode PtInCircle Codegerüst eines ActiveX-Steuerelements hinzufügen. PtInCircle bestimmt, ob die Koordinaten, die an das Steuerelement innerhalb oder außerhalb des Kreises. Dieses Verfahren kann auch verwendet werden, andere benutzerdefinierte Methoden hinzufügen. Ersetzen Sie den Namen Ihrer benutzerdefinierten Methode und seine Parameter für die PtInCircle Methodennamen und Parameter.

> [!NOTE]
>  Dieses Beispiel verwendet die `InCircle` Funktion aus dem Artikel Ereignisse. Weitere Informationen zu dieser Funktion, finden Sie im Artikel [MFC-ActiveX-Steuerelemente: Hinzufügen benutzerdefinierter Ereignisse ein ActiveX-Steuerelement](../mfc/mfc-activex-controls-adding-custom-events.md).

#### <a name="to-add-the-ptincircle-custom-method-using-the-add-method-wizard"></a>Die benutzerdefinierte PtInCircle-Methode, die mithilfe des Assistenten zum Hinzufügen einer Methode hinzufügen

1. Laden Sie das Steuerelementprojekt.

1. Erweitern Sie in der Klassenansicht den Bibliotheksknoten des Steuerelements.

1. Klicken Sie mit der rechten Maustaste auf den Schnittstellenknoten des Steuerelements (den zweiten Knoten des Bibliotheksknotens), um das Kontextmenü zu öffnen.

1. Klicken Sie im Kontextmenü auf **hinzufügen** , und klicken Sie dann auf **Methode hinzufügen**.

     Dies öffnet den Assistenten zum Hinzufügen einer Methode.

1. In der **Methodenname** geben *PtInCircle*.

1. In der **Interner Name** Feld, geben Sie den Namen der internen Funktion der Methode oder den Standardwert (in diesem Fall *PtInCircle*).

1. In der **Rückgabetyp** auf **VARIANT_BOOL** für den Rückgabetyp der Methode.

1. Mithilfe der **Parametertyp** und **Parametername** Steuerelemente hinzufügen, einen Parameter namens *xCoord* (Typ *OLE_XPOS_PIXELS*).

9. Mithilfe der **Parametertyp** und **Parametername** Steuerelemente hinzufügen, einen Parameter namens *dem Namen yCoord* (Typ *OLE_YPOS_PIXELS*).

10. Klicken Sie auf **Fertig stellen**.

##  <a name="_core_classwizard_changes_for_custom_methods"></a> Hinzufügen von Assistenten Änderungen für benutzerdefinierte Methoden

Wenn Sie eine benutzerdefinierte Methode hinzufügen, nimmt der Assistent zum Hinzufügen einer Methode einige Änderungen an dem Control-Header-Klasse (. H) und die Implementierung (. CPP)-Dateien. Die folgende Zeile wird zur Deklaration Dispatch-Zuordnung im Header Steuerelement-Klasse hinzugefügt (. H)-Datei:

[!code-cpp[NVC_MFC_AxUI#18](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-methods_1.h)]

Dieser Code deklariert einen Handler Dispatch-Methode mit dem Namen `PtInCircle`. Diese Funktion kann aufgerufen werden, vom Benutzer Steuerelements, die mit den externen Namen `PtInCircle`.

Die folgende Zeile wird des Steuerelements hinzugefügt. IDL-Datei:

[!code-cpp[NVC_MFC_AxUI#19](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-methods_2.idl)]

Diese Zeile weist den `PtInCircle` Methode einer bestimmten ID-Nummer, die der Position der Methode in der Liste Assistenten zum Hinzufügen von Methoden, Methoden und Eigenschaften. Da der Assistent zum Hinzufügen einer Methode verwendet wurde, um die benutzerdefinierte Methode hinzuzufügen, wurde der Eintrag für diese des Projekts automatisch hinzugefügt. IDL-Datei.

Darüber hinaus die folgende Zeile befindet, in der Implementierung (. CPP)-Datei von der Control-Klasse wird des Steuerelements Dispatchzuordnung hinzugefügt:

[!code-cpp[NVC_MFC_AxUI#20](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-methods_3.cpp)]

Die DISP_FUNCTION-Makro ordnet die Methode `PtInCircle` Handler-Funktion des Steuerelements, `PtInCircle`, deklariert den Rückgabetyp zu sein **VARIANT_BOOL**, und deklariert zwei Parameter vom Typ **VTS_XPOS_PIXELS** und **VTS_YPOSPIXELS** übergeben werden soll `PtInCircle`.

Abschließend fügt der Assistent zum Hinzufügen einer Methode die Stub-Funktion `CSampleCtrl::PtInCircle` am unteren Rand des Steuerelements-Implementierung (. CPP)-Datei. Für `PtInCircle` funktioniert, wie bereits erwähnt, müssen sie wie folgt geändert werden:

[!code-cpp[NVC_MFC_AxUI#21](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-methods_4.cpp)]

## <a name="see-also"></a>Siehe auch

[MFC-ActiveX-Steuerelemente](../mfc/mfc-activex-controls.md)<br/>
[Symbole in der Klassenansicht und im Objektbrowser](/visualstudio/ide/class-view-and-object-browser-icons)

