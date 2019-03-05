---
title: Ziehen und Fallenlassen von Dateien in einem Rahmenfenster
ms.date: 11/04/2016
helpviewer_keywords:
- drag and drop [MFC], files
- drag and drop [MFC], File Manager
- Windows Explorer [MFC]
- File Manager drag and drop support [MFC]
- files [MFC], drag and drop
- frame windows [MFC], dragging and dropping files in
- drag and drop [MFC], Windows Explorer
ms.assetid: 85560fe9-121b-4105-bd7b-216b966e19fa
ms.openlocfilehash: 0129b939e0fe2afd5dd29623bb44418bfd16c20d
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57260408"
---
# <a name="dragging-and-dropping-files-in-a-frame-window"></a>Ziehen und Fallenlassen von Dateien in einem Rahmenfenster

Das Rahmenfenster verwaltet eine Beziehung mit Datei-Explorer oder Datei-Manager.

Durch Hinzufügen von ein paar initialisieren aufruft, in der Überschreibung der der `CWinApp` Memberfunktion `InitInstance`, wie in beschrieben [CWinApp: Die Anwendungsklasse](../mfc/cwinapp-the-application-class.md), dass Ihr Rahmenfenster indirekt Öffnen von Dateien im Datei-Explorer oder Datei-Manager Drag & Drop in das Rahmenfenster. Finden Sie unter [Manager für Dateiserver Drag & Drop](../mfc/special-cwinapp-services.md).

## <a name="see-also"></a>Siehe auch

[Verwenden von Rahmenfenstern](../mfc/using-frame-windows.md)
