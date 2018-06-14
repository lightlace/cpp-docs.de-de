---
title: '&lt;para&gt; (Visual C++) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- <para>
- para
dev_langs:
- C++
helpviewer_keywords:
- <para> C++ XML tag
- para C++ XML tag
ms.assetid: 35f2a1b3-bc14-4f13-bcb0-c39ccbf74d59
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1ebf50e4672ee2a3398f6c484c42f8e36f231169
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33325116"
---
# <a name="ltparagt-visual-c"></a>&lt;para&gt; (Visual C++)
Das Tag \<para> ist für die Verwendung innerhalb eines Tags wie [\<summary>](../ide/summary-visual-cpp.md), [\<remarks>](../ide/remarks-visual-cpp.md) oder [\<returns>](../ide/returns-visual-cpp.md) gedacht und ermöglicht es Ihnen, den Text zu strukturieren.  
  
## <a name="syntax"></a>Syntax  
  
```  
<para>content</para>  
```  
  
#### <a name="parameters"></a>Parameter  
 `content`  
 Der Text des Absatzes  
  
## <a name="remarks"></a>Hinweise  
 Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) kompiliert werden.  
  
## <a name="example"></a>Beispiel  
 Unter [\<summary>](../ide/summary-visual-cpp.md) finden Sie ein Beispiel für die Verwendung von \<para>.  
  
## <a name="see-also"></a>Siehe auch  
 [XML-Dokumentation](../ide/xml-documentation-visual-cpp.md)