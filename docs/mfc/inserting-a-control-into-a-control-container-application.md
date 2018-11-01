---
title: 'ActiveX-Steuerelementcontainer: Einfügen eines Steuerelements in eine Steuerelementcontainer-Anwendung | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ActiveX control containers [MFC], inserting controls
- ActiveX controls [MFC], adding to projects
ms.assetid: bbb617ff-872f-43d8-b4d6-c49adb16b148
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f025c9fa564bcd37c585db6ea5c5cd0f5be83e0d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46432138"
---
# <a name="activex-control-containers-inserting-a-control-into-a-control-container-application"></a>ActiveX-Steuerelementcontainer: Einfügen eines Steuerelements in eine Steuerelementcontainer-Anwendung

Bevor Sie ein ActiveX-Steuerelementcontainer-Anwendung ein ActiveX-Steuerelement zugreifen können, müssen Sie das ActiveX-Steuerelement hinzufügen, auf die Container-Anwendung mithilfe der [ActiveX-Steuerelement einfügen](../windows/insert-activex-control-dialog-box.md) Dialogfeld.

Um die ActiveX-Steuerelement-Container-Projekt ein ActiveX-Steuerelement hinzugefügt haben, finden Sie unter [anzeigen und Hinzufügen von ActiveX-Steuerelementen in einem Dialogfeld](../windows/viewing-and-adding-activex-controls-to-a-dialog-box.md).

Nachdem Sie das Steuerelement hinzugefügt haben, müssen Sie eine Membervariable (des ActiveX-Steuerelements) die Dialogfeldklasse hinzu. Weitere Informationen zu dieser Vorgehensweise finden Sie unter [Hinzufügen einer Membervariablen](../ide/adding-a-member-variable-visual-cpp.md).

Nachdem Sie hinzugefügt haben, der Membervariablen einer Klasse als eine Wrapperklasse, automatisch generiert und Ihrem Projekt hinzugefügt. Diese Klasse dient als Schnittstelle zwischen dem Steuerelementcontainer und das integrierte Steuerelement.

## <a name="see-also"></a>Siehe auch

[ActiveX-Steuerelementcontainer](../mfc/activex-control-containers.md)

