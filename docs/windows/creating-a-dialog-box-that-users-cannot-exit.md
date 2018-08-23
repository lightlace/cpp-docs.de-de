---
title: Erstellen eines Dialogfelds, das Benutzern nicht beendet werden können | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- dialog boxes, creating
- modal dialog boxes, logon screens
- logon screens
ms.assetid: 54823c27-1658-4388-bd12-0a1ce8f3899e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: cd3e68d89ce0a2ece83876b6afcd6aa09e59ed93
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42598219"
---
# <a name="creating-a-dialog-box-that-users-cannot-exit"></a>Erstellen eines Dialogfelds, das vom Benutzer nicht beendet werden kann

Sie können ein Laufzeitdialogfeld erstellen, das von Benutzern nicht beendet werden kann. Diese Art Dialogfeld ist nützlich für Anmeldungen und für Sperren von Anwendungen oder Dokumenten.

### <a name="to-create-a-dialog-box-that-a-user-cannot-exit"></a>So erstellen Sie ein Dialogfeld, das von Benutzern nicht beendet werden kann

1. Legen Sie im Abschnitt **Eigenschaften** des Dialogfelds die Eigenschaft **Systemmenü** auf **falsch**fest.

   Dadurch werden das Systemmenü des Dialogfelds und die Schaltfläche **Schließen** deaktiviert.

2. Löschen Sie auf dem Formular des Dialogfelds die Schaltflächen **Abbrechen** und **OK** .

   Zur Laufzeit kann ein Benutzer ein modales Dialogfeld, das diese Eigenschaften aufweist, nicht beenden.

Zum Testen dieser Art von Dialogfeld zu aktivieren, erkennt der Testfunktion für Dialogfeld Feld beim **Esc** gedrückt wird. (**Esc** ist auch bekannt als die virtuelle Taste "VK_ESCAPE".) Unabhängig davon, wie Sie das Dialogfeld zur Laufzeit Verhalten konzipiert ist, können Sie beenden ihn im Testmodus durch Drücken von **Esc**.

> [!NOTE]
> Für MFC-Anwendungen, um ein Dialogfeld erstellen, die Benutzer nicht beendet werden können, müssen Sie überschreiben das Standardverhalten des `OnOK` und `OnCancel` denn selbst wenn Sie die zugeordneten Schaltflächen löschen, das Dialogfeld immer noch durch Drücken von kann geschlossen werden  **Geben Sie** oder **Esc**.

Weitere Informationen zur Vorgehensweise beim Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index).

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Vorgehensweise: Erstellen einer Ressource](../windows/how-to-create-a-resource.md)  
[Ressourcendateien](../windows/resource-files-visual-studio.md)  
[Dialog-Editor](../windows/dialog-editor.md)