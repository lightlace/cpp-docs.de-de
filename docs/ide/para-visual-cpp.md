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
ms.openlocfilehash: c36388e34b2f1e3cdc4d5664c014463c727e8369
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46385091"
---
# <a name="ltparagt-visual-c"></a>&lt;para&gt; (Visual C++)

Das Tag \<para> ist für die Verwendung innerhalb eines Tags wie [\<summary>](../ide/summary-visual-cpp.md), [\<remarks>](../ide/remarks-visual-cpp.md) oder [\<returns>](../ide/returns-visual-cpp.md) gedacht und ermöglicht es Ihnen, den Text zu strukturieren.

## <a name="syntax"></a>Syntax

```
<para>content</para>
```

#### <a name="parameters"></a>Parameter

*content*<br/>
Der Text des Absatzes

## <a name="remarks"></a>Hinweise

Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) kompiliert werden.

## <a name="example"></a>Beispiel

Unter [\<summary>](../ide/summary-visual-cpp.md) finden Sie ein Beispiel für die Verwendung von \<para>.

## <a name="see-also"></a>Siehe auch

[XML-Dokumentation](../ide/xml-documentation-visual-cpp.md)