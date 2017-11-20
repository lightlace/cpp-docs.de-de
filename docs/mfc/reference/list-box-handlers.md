---
title: Listenfeldhandler | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ON_LBN_DBLCLK
- ON_LBN_ERRSPACE
- ON_LBN_SETFOCUS
- ON_LBN_SELCHANGE
- ON_LBN_KILLFOCUS
dev_langs:
- C++
helpviewer_keywords:
- list boxes [MFC], list box handlers
- ON_LBN_KILLFOCUS
- ON_LBN_ERRSPACE
- ON_LBN_SELCHANGE
- ON_LBN_SETFOCUS
- ON_LBN_DBLCLK
ms.assetid: e4e54412-2167-436a-883b-5dcad01820b8
caps.latest.revision: 11
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 4a770b6508067913aec51b8b3878f33e30eed4bb
ms.openlocfilehash: 2c8aafcabbf4e0049c2e1834803ecded88ccc53d
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="list-box-handlers"></a>Listenfeldhandler
Die folgenden Zuordnungseinträge erhalten den entsprechenden Funktionsprototyp  
  
|Eintrag für die Zuordnung|Funktionsprototyp|  
|---------------|------------------------|  
|ON_LBN_DBLCLK ( \<Id >, \<MemberFxn >)|Afx_msg "void" MemberFxn ();|  
|ON_LBN_ERRSPACE ( \<Id >, \<MemberFxn >)|Afx_msg "void" MemberFxn ();|  
|ON_LBN_KILLFOCUS ( \<Id >, \<MemberFxn >)|Afx_msg "void" MemberFxn ();|  
|ON_LBN_SELCHANGE ( \<Id >, \<MemberFxn >)|Afx_msg "void" MemberFxn ();|  
|ON_LBN_SETFOCUS ( \<Id >, \<MemberFxn >)|Afx_msg "void" MemberFxn ();|  
  
## <a name="see-also"></a>Siehe auch  
 [Meldungszuordnungen](../../mfc/reference/message-maps-mfc.md)

