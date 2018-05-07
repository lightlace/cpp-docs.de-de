---
title: Marshal_context-Klasse | Microsoft Docs
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
ms.openlocfilehash: 6bf712e960cbf96ccef6c3a3e4efebdad9045818
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="marshalcontext-class"></a>marshal_context-Klasse
Diese Klasse konvertiert die Daten zwischen systemeigenen und verwalteten Umgebungen.  
  
## <a name="syntax"></a>Syntax  
  
```  
class marshal_context  
```  
  
## <a name="remarks"></a>Hinweise  
 Verwenden der `marshal_context` Klasse für die Konvertierung von Daten, die einen Kontext benötigen. Finden Sie unter [Overview of Marshaling in C++](../dotnet/overview-of-marshaling-in-cpp.md) erfahren, welche Konvertierungen einen Kontext benötigen und welche Marshalling-Datei enthalten sein muss. Das Ergebnis des Marshallens bei der Verwendung von eines Kontexts ist gültig, bis die `marshal_context` -Objekt zerstört wird. Um Ihr Ergebnis zu erhalten, müssen Sie die Daten kopieren.  
  
 Die gleiche `marshal_context` für mehrere datenkonvertierungen verwendet werden kann. Wiederverwenden von Kontext auf diese Weise wirkt sich nicht auf die Ergebnisse der vorherigen Marshalling aufrufen.  
  
## <a name="requirements"></a>Anforderungen  
 **Headerdatei:** \<msclr\marshal.h >, \<msclr\marshal_windows.h >, \<msclr\marshal_cppstd.h >, oder \<msclr\marshal_atl.h >  
  
 **Namespace:** msclr::interop  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über das Marshaling in C++](../dotnet/overview-of-marshaling-in-cpp.md)   
 [marshal_as](../dotnet/marshal-as.md)