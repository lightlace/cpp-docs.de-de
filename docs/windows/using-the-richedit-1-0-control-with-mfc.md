---
title: Verwenden des RichEdit 1.0-Steuerelements mit MFC | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- RichEdit 1.0 control
- rich edit controls, RichEdit 1.0
ms.assetid: 5a9060dd-44d8-4ef3-956e-16152f7e23d2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a00642c1aefdce57c37723ef4daf23381cee3c13
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2018
ms.locfileid: "39650747"
---
# <a name="using-the-richedit-10-control-with-mfc"></a>Verwenden des RichEdit 1.0-Steuerelements mit MFC
Um ein RichEdit-Steuerelement zu verwenden, müssen Sie zuerst Aufrufen [AfxInitRichEdit2](../mfc/reference/application-information-and-management.md#afxinitrichedit2) beim Laden des RichEdit-2.0-Steuerelements (RICHED20. DLL), oder rufen Sie [AfxInitRichEdit](../mfc/reference/application-information-and-management.md#afxinitrichedit) beim Laden des älteren RichEdit 1.0-Steuerelements (RICHED32. (DLL).  
  
 Möglicherweise verwenden Sie die aktuelle [CRichEditCtrl](../mfc/reference/cricheditctrl-class.md) Klasse mit dem älteren RichEdit 1.0-Steuerelement, aber `CRichEditCtrl` dient nur zur Unterstützung des RichEdit-2.0-Steuerelements. Da RichEdit 1.0 und 2.0 des RichEdit sehr ähnlich sind, funktionieren die meisten Methoden; Beachten Sie jedoch, dass es gibt einige Unterschiede zwischen den Steuerelementen 1.0 und 2.0, sodass einige Methoden möglicherweise nicht ordnungsgemäß oder überhaupt nicht funktionsfähig.  
  
## <a name="requirements"></a>Anforderungen  
 MFC  
  
## <a name="see-also"></a>Siehe auch  
 [Problembehandlung für den Dialog-Editor](../windows/troubleshooting-the-dialog-editor.md)   
 [Dialog-Editor](../windows/dialog-editor.md)