---
title: Bearbeitungssteuerelemente-Handler | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- ON_EN_ERRSPACE
- ON_EN_UPDATE
- ON_EN_VSCROLL
- ON_EN_HSCROLL
- ON_EN_KILLFOCUS
- ON_EN_MAXTEXT
- ON_EN_SETFOCUS
- ON_EN_CHANGE
dev_langs:
- C++
helpviewer_keywords:
- ON_EN_ERRSPACE macro [MFC]
- ON_EN_SETFOCUS macro [MFC]
- ON_EN_UPDATE macro [MFC]
- ON_EN_MAXTEXT macro [MFC]
- ON_EN_CHANGE macro [MFC]
- ON_EN_HSCROLL macro [MFC]
- ON_EN_VSCROLL macro [MFC]
- ON_EN_KILLFOCUS macro [MFC]
- edit controls [MFC], edit control handlers
ms.assetid: 55b88b5e-12b5-4422-b03e-c8c2f27d095c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7e4828eb2241346a0cee4a1d1a732426e28aeb61
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46395322"
---
# <a name="edit-control-handlers"></a>Handler für Bearbeitungssteuerelemente

Die folgenden Zuordnungseinträge entsprechen der Funktionsprototyp.

|Zuordnungseintrag|Funktionsprototyp|
|---------------|------------------------|
|ON_EN_CHANGE ( \<Id >, \<MemberFxn >)|Afx_msg "void" MemberFxn (-);|
|ON_EN_ERRSPACE ( \<Id >, \<MemberFxn >)|Afx_msg "void" MemberFxn (-);|
|ON_EN_HSCROLL ( \<Id >, \<MemberFxn >)|Afx_msg "void" MemberFxn (-);|
|ON_EN_KILLFOCUS ( \<Id >, \<MemberFxn >)|Afx_msg "void" MemberFxn (-);|
|ON_EN_MAXTEXT ( \<Id >, \<MemberFxn >)|Afx_msg "void" MemberFxn (-);|
|ON_EN_SETFOCUS ( \<Id >, \<MemberFxn >)|Afx_msg "void" MemberFxn (-);|
|ON_EN_UPDATE ( \<Id >, \<MemberFxn >)|Afx_msg "void" MemberFxn (-);|
|ON_EN_VSCROLL ( \<Id >, \<MemberFxn >)|Afx_msg "void" MemberFxn (-);|

## <a name="see-also"></a>Siehe auch

[Meldungszuordnungen](../../mfc/reference/message-maps-mfc.md)

