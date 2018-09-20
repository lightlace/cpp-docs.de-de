---
title: 'Marshal_context:: ~ Marshal_context | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- marshal_context::~marshal_context
- msclr.interop.marshal_context.~marshal_context
- marshal_context.~marshal_context
- msclr::interop::marshal_context::~marshal_context
- ~marshal_context
dev_langs:
- C++
helpviewer_keywords:
- marshal_context class [C++], operations
ms.assetid: 34c41b38-4c33-4f61-b74e-831ac46b4ab5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 49f194f153f3e4f911333e22b11ebddf7efcaa32
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46447257"
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