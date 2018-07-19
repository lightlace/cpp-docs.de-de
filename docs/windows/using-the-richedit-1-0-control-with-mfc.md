---
title: Verwenden des RichEdit 1.0-Steuerelements mit MFC | Microsoft Docs
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
ms.openlocfilehash: d2d45de1c6bd986c2bf509ce601f80fcd3721599
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33890310"
---
# <a name="using-the-richedit-10-control-with-mfc"></a>Verwenden des RichEdit 1.0-Steuerelements mit MFC
Um eine RichEdit-Steuerelement verwenden, müssen Sie zuerst Aufrufen [AfxInitRichEdit2](../mfc/reference/application-information-and-management.md#afxinitrichedit2) beim Laden der RichEdit 2.0-Steuerelement (RICHED20. (DLL), oder rufen Sie [AfxInitRichEdit](../mfc/reference/application-information-and-management.md#afxinitrichedit) beim Laden des älteren RichEdit 1.0-Steuerelements (RICHED32. (DLL).  
  
 Möglicherweise verwenden Sie die aktuelle [CRichEditCtrl](../mfc/reference/cricheditctrl-class.md) Klasse mit dem älteren RichEdit 1.0-Steuerelement, aber **CRichEditCtrl** dient nur zur Unterstützung des RichEdit 2.0-Steuerelements. Da RichEdit 1.0 und 2.0 RichEdit sehr ähnlich sind, funktionieren die meisten Methoden; Beachten Sie jedoch, dass es gibt einige Unterschiede zwischen den Steuerelementen 1.0 und 2.0, sodass einige Methoden möglicherweise voll oder fehlerhaft funktionsfähig oder gar nicht funktionsfähig.  
  
## <a name="requirements"></a>Anforderungen  
 MFC  
  
## <a name="see-also"></a>Siehe auch  
 [Problembehandlung für den Dialog-Editor](../windows/troubleshooting-the-dialog-editor.md)   
 [Dialog-Editor](../windows/dialog-editor.md)

