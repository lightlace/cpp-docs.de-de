---
title: Verbinden eines Popupmenüs mit der C++-Anwendung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- pop-up menus [C++], connecting to applications
- context menus [C++], connecting to applications
- menus [C++], pop-up
- shortcut menus [C++], connecting to applications
ms.assetid: 295cbf0e-6416-478e-bc3d-472fb98e0e52
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f1ebb5e2151fe770e6a59210ac564237155fafd4
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46412079"
---
# <a name="connecting-a-pop-up-menu-to-your-c-application"></a>Verbinden eines Popupmenüs mit der C++-Anwendung

### <a name="to-connect-a-pop-up-menu-to-your-application"></a>So verbinden Sie ein Popupmenü mit Ihrer Anwendung

1. Fügen Sie einen Meldungshandler für WM_CONTEXTMENU (z. B.). Weitere Informationen finden Sie unter [Zuordnen von Meldungen zu Funktionen](../mfc/reference/mapping-messages-to-functions.md).

2. Fügen Sie dem Meldungshandler folgenden Code hinzu.

    ```cpp
    CMenu menu;
    VERIFY(menu.LoadMenu(IDR_MENU1));
    CMenu* pPopup = menu.GetSubMenu(0);
    ASSERT(pPopup != NULL);
    pPopup->TrackPopupMenu(TPM_LEFTALIGN | TPM_RIGHTBUTTON, point.x, point.y, AfxGetMainWnd());
    ```

   > [!NOTE]
   > Die [CPoint](../atl-mfc-shared/reference/cpoint-class.md) übergeben durch die Nachricht Handler ist, in Bildschirmkoordinaten.

## <a name="requirements"></a>Anforderungen

MFC

## <a name="see-also"></a>Siehe auch

[Erstellen von Popupmenüs](../windows/creating-pop-up-menus.md)<br/>
[Menü-Editor](../windows/menu-editor.md)  