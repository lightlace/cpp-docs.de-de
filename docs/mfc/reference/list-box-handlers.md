---
title: Listenfeldhandler
ms.date: 11/04/2016
f1_keywords:
- ON_LBN_DBLCLK
- ON_LBN_ERRSPACE
- ON_LBN_SETFOCUS
- ON_LBN_SELCHANGE
- ON_LBN_KILLFOCUS
helpviewer_keywords:
- list boxes [MFC], list box handlers
- ON_LBN_KILLFOCUS
- ON_LBN_ERRSPACE
- ON_LBN_SELCHANGE
- ON_LBN_SETFOCUS
- ON_LBN_DBLCLK
ms.assetid: e4e54412-2167-436a-883b-5dcad01820b8
ms.openlocfilehash: fc126e1bd26da00608bbb7f1239999ca20eb1727
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50637657"
---
# <a name="list-box-handlers"></a>Listenfeldhandler

Die folgenden Zuordnungseinträge müssen den entsprechenden Funktionsprototyp.

|Zuordnungseintrag|Funktionsprototyp|
|---------------|------------------------|
|ON_LBN_DBLCLK ( \<Id >, \<MemberFxn >)|Afx_msg "void" MemberFxn (-);|
|ON_LBN_ERRSPACE ( \<Id >, \<MemberFxn >)|Afx_msg "void" MemberFxn (-);|
|ON_LBN_KILLFOCUS ( \<Id >, \<MemberFxn >)|Afx_msg "void" MemberFxn (-);|
|ON_LBN_SELCHANGE ( \<Id >, \<MemberFxn >)|Afx_msg "void" MemberFxn (-);|
|ON_LBN_SETFOCUS ( \<Id >, \<MemberFxn >)|Afx_msg "void" MemberFxn (-);|

## <a name="see-also"></a>Siehe auch

[Meldungszuordnungen](../../mfc/reference/message-maps-mfc.md)

