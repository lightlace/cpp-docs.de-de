---
title: Auto_inline | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- auto_inline_CPP
- vc-pragma.auto_inline
dev_langs:
- C++
helpviewer_keywords:
- pragmas, auto_inline
- auto_inline pragma
ms.assetid: f7624cd1-be76-429a-881c-65c9040acf43
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cc2fb4cb870ff1dca2f0b55e9aad20741ffb8220
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50083177"
---
# <a name="autoinline"></a>auto_inline
Schließt alle Funktionen innerhalb des Bereichs definiert, in denen **aus** berücksichtigt wird, als Kandidaten für automatische Inlineerweiterung angegeben wird.

## <a name="syntax"></a>Syntax

```
#pragma auto_inline( [{on | off}] )
```

## <a name="remarks"></a>Hinweise

Verwenden der **Auto_inline** Pragma, platzieren Sie es vor und unmittelbar nach (jedoch nicht in) einer Funktionsdefinition. Dieses Pragma tritt mit der ersten Funktionsdefinition in Kraft, nachdem das Pragma angezeigt wird.

## <a name="see-also"></a>Siehe auch

[Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)