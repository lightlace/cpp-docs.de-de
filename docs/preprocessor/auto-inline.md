---
title: auto_inline
ms.date: 11/04/2016
f1_keywords:
- auto_inline_CPP
- vc-pragma.auto_inline
helpviewer_keywords:
- pragmas, auto_inline
- auto_inline pragma
ms.assetid: f7624cd1-be76-429a-881c-65c9040acf43
ms.openlocfilehash: c59dcc8ec7749a91565d5af043b1bd9e9eaa16ea
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62403563"
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