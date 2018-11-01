---
title: Benutzerdefinierte Handler
ms.date: 11/04/2016
f1_keywords:
- vc.mfc.handlers
helpviewer_keywords:
- ON_REGISTERED_MESSAGE macro [MFC]
- ON_MESSAGE macro [MFC]
- user-defined handlers [MFC]
ms.assetid: 99478294-bef0-4ba7-a369-25a6abdcdb62
ms.openlocfilehash: 4d2102668b7cc964e6fe3bffdcc6931a2961a737
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50562252"
---
# <a name="user-defined-handlers"></a>Benutzerdefinierte Handler

Die folgenden Einträge der Karte entsprechen der Funktionsprototypen.

|Zuordnungseintrag|Funktionsprototyp|
|---------------|------------------------|
|ON_MESSAGE ( \<Nachricht >, \<MemberFxn >)|Afx_msg LRESULT MemberFxn (WPARAM, LPARAM);|
|ON_REGISTERED_MESSAGE ( \<nMessageVariable >, \<MemberFxn >)|Afx_msg LRESULT MemberFxn (WPARAM, LPARAM);|
|ON_THREAD_MESSAGE ( \<Nachricht >, \<MemberFxn >)|Afx_msg "void" MemberFxn (WPARAM, LPARAM);|
|ON_REGISTERED_THREAD_MESSAGE ( \<nMessageVariable >, \<MemberFxn >)|Afx_msg "void" MemberFxn (WPARAM, LPARAM);|

## <a name="see-also"></a>Siehe auch

[Meldungszuordnungen](../../mfc/reference/message-maps-mfc.md)<br/>
[Handler für WM_-Meldungen](../../mfc/reference/handlers-for-wm-messages.md)

