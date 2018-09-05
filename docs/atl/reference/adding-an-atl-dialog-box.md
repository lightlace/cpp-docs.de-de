---
title: Hinzufügen einer ATL-Dialogfelds | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- ATL projects, adding dialog resources
- MFC dialog boxes, ATL dialogs
- dialog boxes, ATL
ms.assetid: 152a378f-7b24-4f66-aeba-c740973f03a6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bd34cbcecdcf8943f8a02a2bb82c5c712f2cb16f
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43754721"
---
# <a name="adding-an-atl-dialog-box"></a>Hinzufügen einer ATL-Dialogfelds

Um ein ATL-Dialogfeld zu Ihrem Projekt hinzuzufügen, muss das Projekt entweder ein ATL-Projekt oder einem MFC-Projekt, die ATL-Unterstützung enthält. Sie können den [ATL-Projekt-Assistenten](../../atl/reference/atl-project-wizard.md) zum Erstellen einer ATL-Anwendung verwenden, oder [Ihrer MFC-Anwendung ein ATL-Objekt hinzufügen](../../mfc/reference/adding-atl-support-to-your-mfc-project.md), um die ATL-Unterstützung in einer MFC-Anwendung zu implementieren.

Der ATL-Dialogfeld-Assistent implementiert standardmäßig ein Dialogfeld, das von abgeleiteten [CAxDialogImpl](../../atl/reference/caxdialogimpl-class.md). Diese Klasse enthält Unterstützung für das ActiveX- und Windows-Steuerelemente hosten. Wenn Sie nicht möchten den Aufwand für das ActiveX-Steuerelemente unterstützen, nachdem der Assistent Code generiert wurde, ersetzen Sie alle Instanzen von `CAxDialogImpl` mit [CSimpleDialog](../../atl/reference/csimpledialog-class.md) oder [CDialogImpl](../../atl/reference/cdialogimpl-class.md) als Basisklasse .

> [!NOTE]
>  `CSimpleDialog` erstellt nur modale Dialogfelder, die nur die allgemeine Windows-Steuerelemente zu unterstützen. `CDialogImpl` erstellt entweder modal oder nicht modale Dialogfelder.

### <a name="to-add-an-atl-dialog-resource-to-your-project"></a>Zum Hinzufügen einer ATL-Dialogfeld-Ressource zu Ihrem Projekt

1. Erstellen Sie eine ATL-Projekt mit der [ATL-Projektassistenten](../../atl/reference/atl-project-wizard.md).

2. Von [Klassenansicht](/visualstudio/ide/viewing-the-structure-of-code)mit der rechten Maustaste auf den Projektnamen, und klicken Sie auf **hinzufügen** aus dem Kontextmenü. Klicken Sie auf **hinzufügen**.

3. Im Bereich Vorlagen die [Klasse hinzufügen](../../ide/add-class-dialog-box.md) Dialogfeld klicken Sie auf **ATL-Dialogfeld**. Klicken Sie auf **öffnen** zum Anzeigen der [ATL-Dialogfeld-Assistent](../../atl/reference/atl-dialog-wizard.md).

Weitere Informationen finden Sie unter [Implementieren eines Dialogfelds](../../atl/implementing-a-dialog-box.md).

## <a name="see-also"></a>Siehe auch

[Adding a Class (Hinzufügen einer Klasse)](../../ide/adding-a-class-visual-cpp.md)   
[Fensterklassen](../../atl/atl-window-classes.md)   
[Meldungszuordnungen](../../atl/message-maps-atl.md)

