---
title: Erstellen von nicht modalen Dialogfeldern
ms.date: 11/04/2016
helpviewer_keywords:
- MFC dialog boxes [MFC], modeless
- modeless dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
ms.assetid: 70d78c7f-3d40-477b-9f78-0f33c359f88b
ms.openlocfilehash: 7da6d82257d1407dfcf4d6d3c15cdadbb8c0fa30
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2019
ms.locfileid: "71685665"
---
# <a name="creating-modeless-dialog-boxes"></a>Erstellen von nicht modalen Dialogfeldern

Für ein nicht modalem Dialogfeld müssen Sie in der Dialogfeld Klasse einen eigenen öffentlichen Konstruktor angeben. Um ein nicht modalem Dialogfeld zu erstellen, rufen Sie Ihren öffentlichen Konstruktor auf, und rufen Sie dann die [Create](../mfc/reference/cdialog-class.md#create) Member-Funktion des Dialog Objekts auf, um die Dialog Ressource zu laden. Sie können **Create** entweder während oder nach dem konstruktorbefehl aufzurufen. Wenn die Dialogfeld Ressource die Eigenschaft **WS_VISIBLE**aufweist, wird das Dialogfeld sofort angezeigt. Andernfalls müssen Sie die zugehörige [ShowWindow](../mfc/reference/cwnd-class.md#showwindow) -Member-Funktion aufzurufen.

## <a name="see-also"></a>Siehe auch

[Arbeiten mit Dialog Feldern in MFC](../mfc/life-cycle-of-a-dialog-box.md)
