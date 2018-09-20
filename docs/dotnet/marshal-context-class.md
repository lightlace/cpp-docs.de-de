---
title: Marshal_context-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- marshal_context
dev_langs:
- C++
helpviewer_keywords:
- marshal_context class [C++]
ms.assetid: 241b0cf6-4ca4-4812-aaee-d671c11dc034
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: fc3399ee088a0430ca857c3e421742ee484d337a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46413314"
---
# <a name="marshalcontext-class"></a>marshal_context-Klasse

Diese Klasse konvertiert die Daten zwischen nativen und verwalteten Umgebungen.

## <a name="syntax"></a>Syntax

```
class marshal_context
```

## <a name="remarks"></a>Hinweise

Verwenden der `marshal_context` -Klasse für die Konvertierung von Daten, die einen Kontext erfordern. Finden Sie unter [Overview of Marshaling in C++](../dotnet/overview-of-marshaling-in-cpp.md) für Weitere Informationen, welche Konvertierungen einen Kontext benötigen und welche Marshalling-Datei eingeschlossen werden muss. Das Ergebnis des Marshallens wird bei der Verwendung von eines Kontexts ist nur gültig bis zum die `marshal_context` -Objekt zerstört wird. Um das Ergebnis zu erhalten, müssen Sie die Daten kopieren.

Die gleiche `marshal_context` für mehrere datenkonvertierungen verwendet werden kann. Wiederverwenden von den Kontext auf diese Weise wirkt sich nicht auf die Ergebnisse der vorherigen Marshalling aufrufen.

## <a name="requirements"></a>Anforderungen

**Headerdatei:** \<msclr\marshal.h >, \<msclr\marshal_windows.h >, \<msclr\marshal_cppstd.h >, oder \<msclr\marshal_atl.h >

**Namespace:** msclr::interop

## <a name="see-also"></a>Siehe auch

[Übersicht über das Marshalling in C++](../dotnet/overview-of-marshaling-in-cpp.md)<br/>
[marshal_as](../dotnet/marshal-as.md)