---
title: 'ActiveX-Steuerelementcontainer: Einfügen eines Steuerelements in eine Steuerelementcontainer-Anwendung | Microsoft Docs'
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
ms.openlocfilehash: 716c045fc10b4dd5f3dede20a233d958e669bbd7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33346336"
---
# <a name="activex-control-containers-inserting-a-control-into-a-control-container-application"></a>ActiveX-Steuerelementcontainer: Einfügen eines Steuerelements in eine Steuerelementcontainer-Anwendung
Bevor Sie ein ActiveX-Steuerelement aus einem ActiveX-Steuerelementcontainer-Anwendung zugreifen können, müssen Sie das ActiveX-Steuerelement hinzufügen, die Container-Anwendung über die [ActiveX-Steuerelement einfügen](../windows/insert-activex-control-dialog-box.md) (Dialogfeld).  
  
 Um die ActiveX-Steuerelementcontainer-Projekt ein ActiveX-Steuerelement hinzugefügt haben, finden Sie unter [anzeigen und Hinzufügen von ActiveX-Steuerelementen zu einem Dialogfeld](../windows/viewing-and-adding-activex-controls-to-a-dialog-box.md).  
  
 Nachdem Sie das Steuerelement hinzugefügt haben, müssen Sie die Dialogfeldklasse eine Membervariable (von der ActiveX-Steuerelement-Typ) hinzugefügt. Weitere Informationen zu diesem Verfahren finden Sie unter [Hinzufügen einer Membervariablen](../ide/adding-a-member-variable-visual-cpp.md).  
  
 Nachdem Sie hinzugefügt haben, die Membervariable einer Klasse, die als eine Wrapperklasse bezeichnet wird automatisch generiert und dem Projekt hinzugefügt. Diese Klasse wird als eine Schnittstelle zwischen dem Steuerelementcontainer und dem eingebetteten Steuerelement verwendet.  
  
## <a name="see-also"></a>Siehe auch  
 [ActiveX-Steuerelementcontainer](../mfc/activex-control-containers.md)

