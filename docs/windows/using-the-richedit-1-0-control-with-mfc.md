---
title: Verwenden des RichEdit 1.0-Steuerelements mit MFC
ms.date: 11/04/2016
helpviewer_keywords:
- RichEdit 1.0 control
- rich edit controls [C++], RichEdit 1.0
ms.assetid: 5a9060dd-44d8-4ef3-956e-16152f7e23d2
ms.openlocfilehash: 080ad995b9c7a041337d9b296d6ef8906e7f20ec
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50468314"
---
# <a name="using-the-richedit-10-control-with-mfc"></a>Verwenden des RichEdit 1.0-Steuerelements mit MFC

Um ein RichEdit-Steuerelement zu verwenden, müssen Sie zuerst Aufrufen [AfxInitRichEdit2](../mfc/reference/application-information-and-management.md#afxinitrichedit2) beim Laden des RichEdit-2.0-Steuerelements (RICHED20. DLL), oder rufen Sie [AfxInitRichEdit](../mfc/reference/application-information-and-management.md#afxinitrichedit) beim Laden des älteren RichEdit 1.0-Steuerelements (RICHED32. (DLL).

Möglicherweise verwenden Sie die aktuelle [CRichEditCtrl](../mfc/reference/cricheditctrl-class.md) Klasse mit dem älteren RichEdit 1.0-Steuerelement, aber `CRichEditCtrl` dient nur zur Unterstützung des RichEdit-2.0-Steuerelements. Da RichEdit 1.0 und 2.0 des RichEdit sehr ähnlich sind, funktionieren die meisten Methoden; Beachten Sie jedoch, dass es gibt einige Unterschiede zwischen den Steuerelementen 1.0 und 2.0, sodass einige Methoden möglicherweise nicht ordnungsgemäß oder überhaupt nicht funktionsfähig.

## <a name="requirements"></a>Anforderungen

MFC

## <a name="see-also"></a>Siehe auch

[Problembehandlung beim Dialog-Editor](../windows/troubleshooting-the-dialog-editor.md)<br/>
[Dialog-Editor](../windows/dialog-editor.md)