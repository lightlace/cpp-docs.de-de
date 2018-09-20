---
title: Benutzerdefinierte Handler | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.handlers
dev_langs:
- C++
helpviewer_keywords:
- ON_REGISTERED_MESSAGE macro [MFC]
- ON_MESSAGE macro [MFC]
- user-defined handlers [MFC]
ms.assetid: 99478294-bef0-4ba7-a369-25a6abdcdb62
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 50348d36badb955a14f15e30d846b052b297b4a1
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46442538"
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

