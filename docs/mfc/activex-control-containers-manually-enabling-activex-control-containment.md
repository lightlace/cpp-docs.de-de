---
title: 'ActiveX-Steuerelementcontainer: Manuelles Aktivieren von ActiveX-Steuerelementcontainern'
ms.date: 09/12/2018
helpviewer_keywords:
- AfxEnableControlContainer method [MFC]
- ActiveX control containers [MFC], enabling
- ActiveX controls [MFC], enabling containers
ms.assetid: 833bcde9-c9ad-4709-ad12-2fc2150fb6a5
ms.openlocfilehash: 80ca25192f3dbda711b0398917cfa68571cd2c55
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62394935"
---
# <a name="activex-control-containers-manually-enabling-activex-control-containment"></a>ActiveX-Steuerelementcontainer: Manuelles Aktivieren von ActiveX-Steuerelementcontainern

Wenn Sie ActiveX-Steuerelemente unterstützen, wenn Sie den Assistenten zum MFC-Anwendungen verwendet, um generiert Ihre Anwendung nicht aktiviert haben, müssen Sie diese Unterstützung manuell hinzufügen. Dieser Artikel beschreibt den Prozess zum manuellen Hinzufügen von ActiveX-Steuerelementcontainern zu einer vorhandenen OLE-Container-Anwendung. Wenn Sie im Voraus wissen, dass Sie in der OLE-Container ActiveX-Steuerelemente unterstützen möchten, finden Sie im Artikel [Erstellen eines MFC-ActiveX-Steuerelementcontainers](../mfc/reference/creating-an-mfc-activex-control-container.md).

>[!IMPORTANT]
> ActiveX ist eine veraltete Technologie, die nicht für Neuentwicklungen verwendet werden soll. Weitere Informationen zu moderne Technologien, die ActiveX-ablösen, finden Sie unter [ActiveX-Steuerelemente](activex-controls.md).

> [!NOTE]
>  Diesem Artikel wird ein Dialogfeld-basierte ActiveX-Steuerelementcontainer-Projekt namens "Container" und ein eingebettetes Steuerelement mit dem Namen Circ als Beispiele in den Prozeduren und den Code.

Um ActiveX-Steuerelemente zu unterstützen, müssen Sie eine Codezeile erforderlich, zwei der Dateien des Projekts hinzufügen.

- Ändern des Hauptdialogfelds `InitInstance` -Funktion (wurde im CONTAINER gefunden. CPP) vom MFC-Anwendungs-Assistenten einem Aufruf an [AfxEnableControlContainer](reference/ole-initialization.md#afxenablecontrolcontainer), wie im folgenden Beispiel:

   [!code-cpp[NVC_MFCOleContainer#34](../mfc/codesnippet/cpp/activex-control-containers-manually-enabling-activex-control-containment_1.cpp)]
    [!code-cpp[NVC_MFCOleContainer#35](../mfc/codesnippet/cpp/activex-control-containers-manually-enabling-activex-control-containment_2.cpp)]

- Fügen Sie Folgendes, um Ihres Projekts STDAFX. H-Headerdatei:

   [!code-cpp[NVC_MFCOleContainer#36](../mfc/codesnippet/cpp/activex-control-containers-manually-enabling-activex-control-containment_3.h)]

Erstellen Sie Ihr Projekt, nachdem Sie diese Schritte abgeschlossen haben, neu, indem Sie auf **erstellen** auf die **erstellen** Menü.

## <a name="see-also"></a>Siehe auch

[ActiveX-Steuerelementcontainer](../mfc/activex-control-containers.md)
