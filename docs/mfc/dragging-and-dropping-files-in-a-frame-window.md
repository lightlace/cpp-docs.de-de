---
title: Ziehen und Ablegen von Dateien in einem Rahmenfenster | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- drag and drop [MFC], files
- drag and drop [MFC], File Manager
- Windows Explorer [MFC]
- File Manager drag and drop support [MFC]
- files [MFC], drag and drop
- frame windows [MFC], dragging and dropping files in
- drag and drop [MFC], Windows Explorer
ms.assetid: 85560fe9-121b-4105-bd7b-216b966e19fa
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6fc68923de531240a2d59336c79e54f6562b369c
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46380528"
---
# <a name="dragging-and-dropping-files-in-a-frame-window"></a>Ziehen und Fallenlassen von Dateien in einem Rahmenfenster

Das Rahmenfenster verwaltet eine Beziehung mit Datei-Explorer oder Datei-Manager.

Durch Hinzufügen von ein paar initialisieren aufruft, in der Überschreibung der der `CWinApp` Memberfunktion `InitInstance`, wie in beschrieben [CWinApp: die Anwendungsklasse](../mfc/cwinapp-the-application-class.md), können Sie Ihr Rahmenfenster indirekt Öffnen von Dateien, die aus der Datei gezogen haben Explorer oder Datei-Manager und in das Rahmenfenster gelöscht. Finden Sie unter [Manager für Dateiserver Drag & Drop](../mfc/special-cwinapp-services.md).

## <a name="see-also"></a>Siehe auch

[Verwenden von Rahmenfenstern](../mfc/using-frame-windows.md)

