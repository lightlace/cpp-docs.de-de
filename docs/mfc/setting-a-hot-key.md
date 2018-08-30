---
title: Festlegen einer Abkürzungstaste | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- keyboard shortcuts [MFC], hot keys
- access keys [MFC], hot keys
- CHotKeyCtrl class [MFC], setting hot key
ms.assetid: 6f3bc141-e346-4dce-9ca7-3e6b2c453f3f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 254d7532b83a4f30c0029b2488bb0b2111cce31d
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43219396"
---
# <a name="setting-a-hot-key"></a>Festlegen einer Abkürzungstaste
Die Anwendung kann mithilfe die Informationen von einer Abkürzungstaste ([CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)) Steuerelement auf zwei Arten:  
  
-   Richten Sie eine globale Abkürzungstaste für die Aktivierung eines nicht untergeordneten Fensters durch Senden einer [WM_SETHOTKEY](/windows/desktop/inputdev/wm-sethotkey) Nachricht an das Fenster aktiviert wird.  
  
-   Festlegen einer Abkürzungstaste threadspezifische durch Aufrufen der Windows-Funktion [RegisterHotKey](https://msdn.microsoft.com/library/windows/desktop/ms646309).  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CHotKeyCtrl](../mfc/using-chotkeyctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

