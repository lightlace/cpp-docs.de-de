---
title: Zerstören des Listensteuerelements | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- list controls [MFC], destroying
- CListCtrl class [MFC], destroying controls
ms.assetid: 513ec820-3a02-49d2-b073-a6a7a3fc91b3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 25642357e3dd9117ae2817307ed5fa3c4a0921d0
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46424537"
---
# <a name="destroying-the-list-control"></a>Zerstören des Listensteuerelements

Wenn Sie einbetten Ihrer [CListCtrl](../mfc/reference/clistctrl-class.md) als Datenmember einer Klasse Ansichts- oder Dialogfeldobjekt Objekt zerstört wird, wenn der Besitzer zerstört wird. Bei Verwendung einer [CListView](../mfc/reference/clistview-class.md), das Framework zerstört das Steuerelement beim Zerstören der Ansicht.

Wenn Sie für Ihre Liste-Daten in die Anwendung statt auf das Strukturelement-Steuerelement zu speichernde anordnen möchten, müssen Sie für deren Freigabe gesorgt. Weitere Informationen finden Sie unter [Rückrufelemente und Rückrufmaske](/windows/desktop/Controls/using-list-view-controls) im Windows SDK.

Darüber hinaus sind Sie verantwortlich für das Aufheben der Zuordnung Bildlisten, die Sie erstellt und mit dem Listensteuerelement-Objekt verknüpft.

## <a name="see-also"></a>Siehe auch

[Verwenden von CListCtrl](../mfc/using-clistctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)

