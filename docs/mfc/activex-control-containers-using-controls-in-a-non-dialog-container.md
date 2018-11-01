---
title: 'ActiveX-Steuerelementcontainer: Verwenden von Steuerelementen in Containern, die keine Dialogfelder sind'
ms.date: 11/04/2016
helpviewer_keywords:
- Create method [MFC], ActiveX controls
- CreateControl method [MFC]
- ActiveX controls [MFC], creating
- ActiveX control containers [MFC], non-dialog containers
- ActiveX control containers [MFC], inserting controls
ms.assetid: 46f195b0-b8ca-4409-8cca-fbfaf2c9ab9f
ms.openlocfilehash: b31581b77743104a92236336c4db380f1693ea55
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50538787"
---
# <a name="activex-control-containers-using-controls-in-a-non-dialog-container"></a>ActiveX-Steuerelementcontainer: Verwenden von Steuerelementen in Containern, die keine Dialogfelder sind

In einige Anwendungen, z. B. eine SDI und MDI-Anwendung werden Sie ein Steuerelement in einem Fenster der Anwendung einbetten möchten. Die **erstellen** Memberfunktion der Wrapperklasse, die von Visual C++ eingefügt kann eine Instanz des Steuerelements dynamisch erstellen, ohne ein Dialogfeld.

Die **erstellen** Member-Funktion weist die folgenden Parameter:

*lpszWindowName*<br/>
Ein Zeiger auf den Text in die Eigenschaft des Steuerelements oder Beschriftungstitel (sofern vorhanden) angezeigt werden.

*dwStyle*<br/>
Windows-Formate. Eine vollständige Liste finden Sie unter [CWnd:: CreateControl](../mfc/reference/cwnd-class.md#createcontrol).

*Rect*<br/>
Gibt an, die Größe und Position des Steuerelements.

*pParentWnd*<br/>
Gibt an, das Steuerelement für die übergeordnete Fenster, in der Regel eine `CDialog`. Er darf nicht sein **NULL**.

*nID*<br/>
Gibt an, die Steuerelement-ID, und kann vom Container verwendet werden, um auf das Steuerelement zu verweisen.

Ein Beispiel für diese Funktion verwenden, um ein ActiveX-Steuerelement dynamisch zu erstellen, wäre in einer Formularansicht einer SDI-Anwendung. Sie können dann erstellen Sie eine Instanz des Steuerelements in der `WM_CREATE` Handler der Anwendung.

In diesem Beispiel `CMyView` ist die zentrale View-Klasse, `CCirc` ist eine Wrapperklasse und CIRC. H ist der Header (. H)-Datei der Wrapperklasse.

Diese Funktion ist ein Prozess mit vier Schritten.

### <a name="to-dynamically-create-an-activex-control-in-a-non-dialog-window"></a>Um ein ActiveX-Steuerelement in einem nicht-Dialogfeld dynamisch zu erstellen

1. Fügen Sie CIRC. H im CMYVIEW. H, kurz bevor die `CMyView` Definition der Klasse:

   [!code-cpp[NVC_MFC_AxCont#12](../mfc/codesnippet/cpp/activex-control-containers-using-controls-in-a-non-dialog-container_1.h)]

1. Hinzufügen eine Membervariablen (des Typs `CCirc`) zum geschützten Abschnitt von der `CMyView` befindet sich in CMYVIEW Definition der Klasse. H:

   [!code-cpp[NVC_MFC_AxCont#13](../mfc/codesnippet/cpp/activex-control-containers-using-controls-in-a-non-dialog-container_2.h)]
    [!code-cpp[NVC_MFC_AxCont#14](../mfc/codesnippet/cpp/activex-control-containers-using-controls-in-a-non-dialog-container_3.h)]

1. Hinzufügen einer `WM_CREATE` Meldungshandler Klasse `CMyView`.

1. In der Handlerfunktion `CMyView::OnCreate`, einen Aufruf des Steuerelements `Create` -Funktion mit den **dies** Zeiger als das übergeordnete Fenster:

   [!code-cpp[NVC_MFC_AxCont#15](../mfc/codesnippet/cpp/activex-control-containers-using-controls-in-a-non-dialog-container_4.cpp)]

1. Erstellen Sie das Projekt neu. Ein Circ-Steuerelement wird dynamisch erstellt werden, wenn die Anwendungsansicht erstellt wird.

## <a name="see-also"></a>Siehe auch

[ActiveX-Steuerelementcontainer](../mfc/activex-control-containers.md)

