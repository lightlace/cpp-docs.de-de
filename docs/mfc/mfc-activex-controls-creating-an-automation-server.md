---
title: 'MFC-ActiveX-Steuerelemente: Erstellen eines Automatisierungsservers | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Automation servers [MFC], MFC ActiveX controls
- ActiveX controls [MFC], Automation server
- MFC ActiveX controls [MFC], Automation server
ms.assetid: e0c24ed2-d61c-49ad-a4fa-4e1098d1d39b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e37e6183ca840067ceca47dd48f3b24d7b3b98c7
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50074539"
---
# <a name="mfc-activex-controls-creating-an-automation-server"></a>MFC-ActiveX-Steuerelemente: Erstellen eines Automatisierungsservers

Sie können ein MFC-ActiveX-Steuerelement als Automatisierungsserver programmgesteuert das Steuerelement in einer anderen Anwendung einbetten und Aufrufen von Methoden in das Steuerelement aus der Anwendung entwickeln. Z. B. ein Steuerelement würde weiterhin für das Hosten in einem ActiveX-Steuerelementcontainer verfügbar sein.

### <a name="to-create-a-control-as-an-automation-server"></a>So erstellen Sie ein Steuerelement als Automatisierungsserver

1. [Erstellen Sie](../mfc/reference/mfc-activex-control-wizard.md) des Steuerelements.

1. [Fügen Sie Methoden](../mfc/mfc-activex-controls-methods.md).

1. Außer Kraft setzen [Sie IsInvokeAllowed](../mfc/reference/colecontrol-class.md#isinvokeallowed).

1. Erstellen Sie das Steuerelement.

### <a name="to-programmatically-access-the-methods-in-an-automation-server"></a>Um programmgesteuert auf die Methoden in einem Automatisierungsserver zugreifen

1. Erstellen Sie eine Anwendung, z. B., eine [MFC-Exe](../mfc/reference/mfc-application-wizard.md).

1. Am Anfang der `InitInstance` funktioniert, fügen Sie die folgende Zeile hinzu:

   [!code-cpp[NVC_MFC_AxCont#17](../mfc/codesnippet/cpp/mfc-activex-controls-creating-an-automation-server_1.cpp)]

1. Klicken Sie in der Klassenansicht mit der rechten Maustaste des Projektknotens, und wählen **Hinzufügen von Klassen aus der Typbibliothek** zum Importieren der Typbibliothek.

   Dadurch wird dem Projekt Dateien mit der Datei Namen Erweiterungen h- und cpp hinzugefügt.

1. In der Headerdatei der-Klasse, Sie eine oder mehrere Methoden in das ActiveX-Steuerelement rufen, fügen Sie die folgende Zeile: `#include filename.h`, wobei der Dateiname der Name der Headerdatei ist, die beim Importieren der Typbibliothek erstellt wurde.

1. Klicken Sie in der Funktion an eine Methode in das ActiveX-Steuerelement, in denen kein Anruf ausgeführt wird, fügen Sie Code, der ein Objekt der Klasse des Steuerelements Wrapper erstellt, und erstellen Sie das ActiveX-Objekt. Zum Beispiel instanziiert der folgende MFC-Code eine `CCirc` -Steuerelement ruft die Caption-Eigenschaft, und das Ergebnis wird angezeigt, wenn in einem Dialogfeld die Schaltfläche "OK" geklickt wird:

   [!code-cpp[NVC_MFC_AxCont#18](../mfc/codesnippet/cpp/mfc-activex-controls-creating-an-automation-server_2.cpp)]

Wenn Sie Methoden auf das ActiveX-Steuerelement hinzufügen, nachdem Sie ihn in einer Anwendung verwenden, können Sie beginnen, verwenden die neueste Version des Steuerelements in der Anwendung durch Löschen der Dateien, die beim Importieren der Typbibliothek erstellt wurden. Importieren Sie die Typbibliothek wird dann erneut.

## <a name="see-also"></a>Siehe auch

[MFC-ActiveX-Steuerelemente](../mfc/mfc-activex-controls.md)

