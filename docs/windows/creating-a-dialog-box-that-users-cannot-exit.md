---
title: Erstellen eines Dialogfelds, die Benutzer nicht beendet werden können | Microsoft Docs
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
ms.openlocfilehash: fc04c9ccfb0fdc74e57142bf746681411bbba495
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33884462"
---
# <a name="creating-a-dialog-box-that-users-cannot-exit"></a>Erstellen eines Dialogfelds, das vom Benutzer nicht beendet werden kann
Sie können ein Laufzeitdialogfeld erstellen, das von Benutzern nicht beendet werden kann. Diese Art Dialogfeld ist nützlich für Anmeldungen und für Sperren von Anwendungen oder Dokumenten.  
  
### <a name="to-create-a-dialog-box-that-a-user-cannot-exit"></a>So erstellen Sie ein Dialogfeld, das von Benutzern nicht beendet werden kann  
  
1.  Legen Sie im Abschnitt **Eigenschaften** des Dialogfelds die Eigenschaft **Systemmenü** auf **falsch**fest.  
  
     Dadurch werden das Systemmenü des Dialogfelds und die Schaltfläche **Schließen** deaktiviert.  
  
2.  Löschen Sie auf dem Formular des Dialogfelds die Schaltflächen **Abbrechen** und **OK** .  
  
     Zur Laufzeit kann ein Benutzer ein modales Dialogfeld, das diese Eigenschaften aufweist, nicht beenden.  
  
 Um das Testen dieser Art von Dialogfeldern zu ermöglichen, erkennt die Funktion zum Testen von Dialogfeldern, wenn ESC gedrückt wird. (ESC wird auch als virtuelle Taste „VK_ESCAPE“ bezeichnet.) Unabhängig davon, wie das Laufzeitverhalten des Dialogfelds ausgelegt wurde, im Testmodus können Sie es durch Drücken von ESC beenden.  
  
> [!NOTE]
>  Um bei MFC-Anwendungen ein Dialogfeld zu erstellen, das von Benutzern nicht beendet werden kann, müssen Sie das Standardverhalten von `OnOK` und `OnCancel` außer Kraft setzen, denn selbst wenn Sie die zugeordneten Schaltflächen löschen, kann das Dialogfeld immer noch durch Drücken von EINGABETASTE oder ESC geschlossen werden.  
  
 Informationen zur Vorgehensweise beim Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index).  
  
## <a name="requirements"></a>Anforderungen  
 Win32  
  
## <a name="see-also"></a>Siehe auch  
 [Vorgehensweise: Erstellen einer Ressource](../windows/how-to-create-a-resource.md)   
 [Ressourcendateien](../windows/resource-files-visual-studio.md)   
 [Dialog-Editor](../windows/dialog-editor.md)

