---
title: '&lt;remarks&gt; (Visual C++) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- remarks
- <remarks>
dev_langs:
- C++
helpviewer_keywords:
- <remarks> C++ XML tag
- remarks C++ XML tag
ms.assetid: c820083b-3192-40ab-9ec8-1472c55b4247
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 409f10dffdf6816f3ff0ab4e71060c9bcb6eaf9f
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43684211"
---
# <a name="ltremarksgt-visual-c"></a>&lt;remarks&gt; (Visual C++)
Das Tag \<remarks> wird verwendet, um Informationen zu einem Typ hinzuzufügen. Dadurch werden die mit [\<summary>](../ide/summary-visual-cpp.md) angegebenen Informationen ergänzt. Diese Informationen werden im [Objektkatalog](/visualstudio/ide/viewing-the-structure-of-code) und im Webbericht über Codekommentare angezeigt.  
  
## <a name="syntax"></a>Syntax  
  
```  
<remarks>description</remarks>  
```  
  
#### <a name="parameters"></a>Parameter  
 `description`  
 Eine Beschreibung des Members  
  
## <a name="remarks"></a>Hinweise  
 Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) kompiliert werden.  
  
## <a name="example"></a>Beispiel  
  
```  
// xml_remarks_tag.cpp  
// compile with: /LD /clr /doc  
// post-build command: xdcmake xml_remarks_tag.dll  
  
using namespace System;  
  
/// <summary>  
/// You may have some primary information about this class.  
/// </summary>  
/// <remarks>  
/// You may have some additional information about this class.  
/// </remarks>  
public ref class MyClass {};  
```  
  
## <a name="see-also"></a>Siehe auch  
 [XML-Dokumentation](../ide/xml-documentation-visual-cpp.md)