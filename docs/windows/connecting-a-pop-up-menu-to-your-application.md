---
title: Verbinden eines Popupmenüs mit der C++-Anwendung
ms.date: 11/04/2016
helpviewer_keywords:
- pop-up menus [C++], connecting to applications
- context menus [C++], connecting to applications
- menus [C++], pop-up
- shortcut menus [C++], connecting to applications
ms.assetid: 295cbf0e-6416-478e-bc3d-472fb98e0e52
ms.openlocfilehash: 8a0cb64caaa58b464b0d5abb52093350c5e3cfeb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50556493"
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