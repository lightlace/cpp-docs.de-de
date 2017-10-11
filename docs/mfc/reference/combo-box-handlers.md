---
title: Kombinationsfeldhandler | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ON_CBN_KILLFOCUS
- ON_CBN_ERRSPACE
- ON_CBN_EDITCHANGE
- ON_CBN_CLOSEUP
- ON_CBN_DBLCLK
- ON_CBN_EDITUPDATE
- ON_CBN_DROPDOWN
- ON_CBN_SELENDOK
- ON_CBN_SELCHANGE
- ON_CBN_SETFOCUS
- ON_CBN_SELENDCANCEL
dev_langs:
- C++
helpviewer_keywords:
- ON_CBN_CLOSEUP
- ON_CBN_SETFOCUS
- ON_CBN_DBLCLK
- ON_CBN_SELENDCANCEL
- ON_CBN_DROPDOWN
- ON_CBN_EDITUPDATE
- ON_CBN_KILLFOCUS
- combo boxes [MFC], handlers
- ON_CBN_EDITCHANGE
- ON_CBN_ERRSPACE
- ON_CBN_SELENDOK
- ON_CBN_SELCHANGE
ms.assetid: 7f092412-01b7-4242-95ec-41ba506b9d71
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 4a770b6508067913aec51b8b3878f33e30eed4bb
ms.openlocfilehash: 70c4e1f8bc553d155aa21879f986c4361f15a2ae
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="combo-box-handlers"></a>Kombinationsfeldhandler
Die folgenden Zuordnungseinträge entsprechen der Funktionsprototypen.  
  
|Eintrag für die Zuordnung|Funktionsprototyp|  
|---------------|------------------------|  
|ON_CBN_CLOSEUP ( \<Id >, \<MemberFxn >)|Afx_msg "void" MemberFxn)|  
|ON_CBN_DBLCLK ( \<Id >, \<MemberFxn >)|Afx_msg "void" MemberFxn ();|  
|ON_CBN_DROPDOWN ( \<Id >, \<MemberFxn >)|Afx_msg "void" MemberFxn ();|  
|ON_CBN_EDITCHANGE ( \<Id >, \<MemberFxn >)|Afx_msg "void" MemberFxn ();|  
|ON_CBN_EDITUPDATE ( \<Id >, \<MemberFxn >)|Afx_msg "void" MemberFxn ();|  
|ON_CBN_ERRSPACE ( \<Id >, \<MemberFxn >)|Afx_msg "void" MemberFxn ();|  
|ON_CBN_KILLFOCUS ( \<Id >, \<MemberFxn >)|Afx_msg "void" MemberFxn ();|  
|ON_CBN_SELCHANGE ( \<Id >, \<MemberFxn >)|Afx_msg "void" MemberFxn ();|  
|ON_CBN_SELENDCANCEL ( \<Id >, \<MemberFxn >)|Afx_msg "void" MemberFxn ();|  
|ON_CBN_SELENDOK ( \<Id >, \<MemberFxn >)|Afx_msg "void" MemberFxn ();|  
|ON_CBN_SETFOCUS ( \<Id >, \<MemberFxn >)|Afx_msg "void" MemberFxn ();|  
  
## <a name="see-also"></a>Siehe auch  
 [Meldungszuordnungen](../../mfc/reference/message-maps-mfc.md)


