---
title: marshal_context::marshal_context
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- msclr::interop::marshal_context::marshal_context
- marshal_context::marshal_context
- msclr.interop.marshal_context.marshal_context
- marshal_context.marshal_context
helpviewer_keywords:
- marshal_context class [C++], operations
ms.assetid: 5f08c895-60b0-4f72-97ff-7ae37c68e853
ms.openlocfilehash: a1a62c47450224aa2bcacde75038adf7a8cfbb9d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50532586"
---
# <a name="marshalcontextmarshalcontext"></a>marshal_context::marshal_context

Erstellt eine `marshal_context` Objekt, für die Datenkonvertierung zwischen verwalteten und systemeigenen Datentypen verwendet werden.

## <a name="syntax"></a>Syntax

```
marshal_context();
```

## <a name="remarks"></a>Hinweise

Einige datenkonvertierungen erfordern einen Kontext gemarshallt. Finden Sie unter [Overview of Marshaling in C++](../dotnet/overview-of-marshaling-in-cpp.md) für Weitere Informationen zu der Übersetzungen einen Kontext benötigen und welche Marshalling-Datei muss in Ihrer Anwendung einbezogen werden.

## <a name="example"></a>Beispiel

Siehe das Beispiel für [marshal_context::marshal_as](../dotnet/marshal-context-marshal-as.md).

## <a name="requirements"></a>Anforderungen

**Headerdatei:** \<msclr\marshal.h >, \<msclr\marshal_windows.h >, \<msclr\marshal_cppstd.h >, oder \<msclr\marshal_atl.h >

**Namespace:** msclr::interop

## <a name="see-also"></a>Siehe auch

[Übersicht über das Marshalling in C++](../dotnet/overview-of-marshaling-in-cpp.md)<br/>
[marshal_as](../dotnet/marshal-as.md)<br/>
[marshal_context-Klasse](../dotnet/marshal-context-class.md)