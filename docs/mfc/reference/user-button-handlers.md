---
title: "Benutzerschaltflächen | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ON_BN_HILITE
- ON_BN_DOUBLECLICKED
- ON_BN_CLICKED
- ON_BN_PAINT
- ON_BN_DISABLE
- ON_BN_UNHILITE
dev_langs:
- C++
helpviewer_keywords:
- ON_BN_PAINT
- user buttons [MFC]
- ON_BN_DOUBLECLICKED [MFC]
- ON_BN_DISABLE [MFC]
- ON_BN_UNHILITE [MFC]
- ON_BN_HILITE [MFC]
- ON_BN_CLICKED [MFC]
ms.assetid: 410ea968-478f-4806-b7b8-5d7c8dc2bf42
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 4a770b6508067913aec51b8b3878f33e30eed4bb
ms.openlocfilehash: eb5acc7a127af69d65536d131f9b388b4f4ff8f9
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="user-button-handlers"></a>Handler für Benutzerschaltflächen
Die folgenden Zuordnungseinträge entsprechen der Funktionsprototypen.  
  
|Eintrag für die Zuordnung|Funktionsprototyp|  
|---------------|------------------------|  
|ON_BN_CLICKED ( \<Id >, \<MemberFxn >)|Afx_msg "void" MemberFxn ();|  
|ON_BN_DISABLE ( \<Id >, \<MemberFxn >)|Afx_msg "void" MemberFxn ();|  
|ON_BN_DOUBLECLICKED ( \<Id >, \<MemberFxn >)|Afx_msg "void" MemberFxn ();|  
|ON_BN_HILITE ( \<Id >, \<MemberFxn >)|Afx_msg "void" MemberFxn ();|  
|ON_BN_PAINT ( \<Id >, \<MemberFxn >)|Afx_msg "void" MemberFxn ();|  
|ON_BN_UNHILITE ( \<Id >, \<MemberFxn >)|Afx_msg "void" MemberFxn ();|  
  
## <a name="see-also"></a>Siehe auch  
 [Meldungszuordnungen](../../mfc/reference/message-maps-mfc.md)


