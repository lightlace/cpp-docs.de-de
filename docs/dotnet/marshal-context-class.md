---
title: marshal_context-Klasse
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- marshal_context
helpviewer_keywords:
- marshal_context class [C++]
ms.assetid: 241b0cf6-4ca4-4812-aaee-d671c11dc034
ms.openlocfilehash: 0e25aee0996b0cd16ca92566da22d377b762d7bc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50594531"
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