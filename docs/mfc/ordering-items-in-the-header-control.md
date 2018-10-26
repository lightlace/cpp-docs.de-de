---
title: Anordnen von Elementen im Headersteuerelement | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- DS_DRAGDROP
dev_langs:
- C++
helpviewer_keywords:
- sequence [MFC]
- sequence [MFC], header control items
- OrderToIndex method [MFC]
- DS_DRAGDROP notification [MFC]
- GetOrderArray method [MFC]
- SetOrderArray method [MFC]
- header controls [MFC], ordering items
ms.assetid: 5aaef872-75b5-49c5-8fed-6f9a81fca812
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 60139821c1b15673fac0fb8f9ec3925cbfa6dc31
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50052096"
---
# <a name="ordering-items-in-the-header-control"></a>Anordnen von Elementen im Headersteuerelement

Nachdem Sie haben [einem Kopfzeilen-Steuerelement Elemente hinzugefügt](../mfc/adding-items-to-the-header-control.md), können Sie bearbeiten oder Abrufen von Informationen zu deren Reihenfolge mit den folgenden Funktionen:

- [CHeaderCtrl:: GetOrderArray](../mfc/reference/cheaderctrl-class.md#getorderarray) und [CHeaderCtrl::SetOrderArray](../mfc/reference/cheaderctrl-class.md#setorderarray)

   Ruft ab, und die links-nach-rechts-Reihenfolge der Headerelemente festgelegt.

- [CHeaderCtrl::OrderToIndex](../mfc/reference/cheaderctrl-class.md#ordertoindex).

   Ruft den Indexwert für ein bestimmtes Headerelement ab.

Zusätzlich zu den vorherigen Memberfunktionen kann die HDS_DRAGDROP-Stil den Benutzer Drag & drop-Header-Elemente, in dem Kopfzeilen-Steuerelement. Weitere Informationen finden Sie unter [Bereitstellen von Drag & Drop-Unterstützung für Headerelemente](../mfc/providing-drag-and-drop-support-for-header-items.md).

## <a name="see-also"></a>Siehe auch

[Verwenden von CHeaderCtrl](../mfc/using-cheaderctrl.md)

