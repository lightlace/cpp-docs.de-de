---
title: marshal_context::~marshal_context
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- marshal_context::~marshal_context
- msclr.interop.marshal_context.~marshal_context
- marshal_context.~marshal_context
- msclr::interop::marshal_context::~marshal_context
- ~marshal_context
helpviewer_keywords:
- marshal_context class [C++], operations
ms.assetid: 34c41b38-4c33-4f61-b74e-831ac46b4ab5
ms.openlocfilehash: 3bf16ab2dde4047fb845cd700821d097f733a4d2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50528218"
---
# <a name="marshalcontextmarshalcontext"></a>marshal_context::~marshal_context

Zerstört ein `marshal_context`-Objekt.

## <a name="syntax"></a>Syntax

```
~marshal_context();
```

## <a name="remarks"></a>Hinweise

Einige datenkonvertierungen erfordern einen Kontext gemarshallt. Finden Sie unter [Overview of Marshaling in C++](../dotnet/overview-of-marshaling-in-cpp.md) für Weitere Informationen zu der Übersetzungen einen Kontext benötigen und welche Marshalling-Datei muss in Ihrer Anwendung einbezogen werden.

Löschen einer `marshal_context` Objekt werden die Daten konvertiert, die von diesem Kontext ungültig. Wenn Sie Ihre Daten nach dem beibehalten möchten eine `marshal_context` -Objekt zerstört wird, müssen Sie die Daten manuell kopieren, auf eine Variable, die beibehalten werden.

## <a name="requirements"></a>Anforderungen

**Headerdatei:** \<msclr\marshal.h >, \<msclr\marshal_windows.h >, \<msclr\marshal_cppstd.h >, oder \<msclr\marshal_atl.h >

**Namespace:** msclr::interop

## <a name="see-also"></a>Siehe auch

[Übersicht über das Marshalling in C++](../dotnet/overview-of-marshaling-in-cpp.md)<br/>
[marshal_as](../dotnet/marshal-as.md)<br/>
[marshal_context-Klasse](../dotnet/marshal-context-class.md)