---
title: Zugreifen auf Laufzeit-Klasseninformationen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CObject class [MFC], and RTTI
- CObject class [MFC], using IsKindOf method [MFC]
- run time [MFC], class information
- RUNTIME_CLASS macro [MFC]
- CObject class [MFC], using RUNTIME_CLASS macro [MFC]
- RTTI compiler option [MFC]
- CObject class [MFC], accessing run-time class information
- run time [MFC]
- IsKindOf method method [MFC]
- run-time class [MFC], accessing information
- classes [MFC], run-time class information
- run-time class [MFC]
- RUNTIME_CLASS macro, using
ms.assetid: 3445a9af-0bd6-4496-95c3-aa59b964570b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 947102f17a5f35b7e6b5266f637375982d4cd55f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="accessing-run-time-class-information"></a>Zugreifen auf Laufzeit-Klasseninformationen
In diesem Artikel wird erläutert, wie Zugriff auf Informationen über die Klasse eines Objekts zur Laufzeit.  
  
> [!NOTE]
>  MFC verwendet nicht die [-Laufzeit-Typinformationen](../cpp/run-time-type-information.md) (RTTI)-Unterstützung in Visual C++ 4.0 eingeführt.  
  
 Wenn Sie eine Klasse von abgeleiteten [CObject](../mfc/reference/cobject-class.md) und verwendet die **DECLARE**_**dynamische** und `IMPLEMENT_DYNAMIC`, `DECLARE_DYNCREATE` und `IMPLEMENT_DYNCREATE`, oder die `DECLARE_SERIAL` und `IMPLEMENT_SERIAL` Makros im Artikel erläutert [Ableiten einer Klasse von CObject](../mfc/deriving-a-class-from-cobject.md), `CObject` -Klasse verfügt über die Möglichkeit, die genaue Klasse eines Objekts zur Laufzeit zu bestimmen.  
  
 Diese Funktion ist besonders hilfreich, wenn zusätzlichen typüberprüfung für Argumente der Funktion erforderlich ist und Sie spezielle Code basierend auf der Klasse eines Objekts schreiben müssen. Allerdings ist dies nicht in der Regel empfohlen, da es die Funktionalität von virtuellen Funktionen dupliziert.  
  
 Die `CObject` Memberfunktion `IsKindOf` können verwendet werden, um festzustellen, ob ein bestimmtes Objekt zu einer bestimmten Klasse gehört, oder wenn es von einer bestimmten Klasse abgeleitet ist. Das Argument für `IsKindOf` ist ein `CRuntimeClass` -Objekt, das Sie mit der `RUNTIME_CLASS` Makro mit dem Namen der Klasse.  
  
### <a name="to-use-the-runtimeclass-macro"></a>Verwenden Sie das RUNTIME_CLASS-Makro  
  
1.  Verwendung `RUNTIME_CLASS` mit dem Namen der Klasse, wie hier gezeigt für die Klasse `CObject`:  
  
     [!code-cpp[NVC_MFCCObjectSample#4](../mfc/codesnippet/cpp/accessing-run-time-class-information_1.cpp)]  
  
 Sie müssen nur selten jedoch stattdessen das Run-Time-Klasse direkt zugreifen. Wird einem häufiger verwendet, um die Run-Time-Klasse-Objekt an den `IsKindOf` -Funktion wie auch in der nächsten Prozedur gezeigt. Die `IsKindOf` Funktion testet ein Objekt, um festzustellen, ob es zu einer bestimmten Klasse gehört.  
  
#### <a name="to-use-the-iskindof-function"></a>Verwenden die IsKindOf-Funktion  
  
1.  Stellen Sie sicher, dass die Klasse Laufzeitklasse Unterstützung verfügt. Also die Klasse muss abgeleitet sein direkt oder indirekt aus `CObject` und verwendet die **DECLARE**_**dynamische** und `IMPLEMENT_DYNAMIC`, `DECLARE_DYNCREATE` und `IMPLEMENT_DYNCREATE`, oder die `DECLARE_SERIAL` und `IMPLEMENT_SERIAL` Makros im Artikel erläutert [Ableiten einer Klasse von CObject](../mfc/deriving-a-class-from-cobject.md).  
  
2.  Rufen Sie die `IsKindOf` Memberfunktion für Objekte dieser Klasse mithilfe der `RUNTIME_CLASS` Makro zum Generieren der `CRuntimeClass` -Arguments zu, wie hier gezeigt:  
  
     [!code-cpp[NVC_MFCCObjectSample#2](../mfc/codesnippet/cpp/accessing-run-time-class-information_2.h)]  
  
     [!code-cpp[NVC_MFCCObjectSample#5](../mfc/codesnippet/cpp/accessing-run-time-class-information_3.cpp)]  
  
    > [!NOTE]
    >  IsKindOf gibt **"true"** , wenn das Objekt ein Element der angegebenen Klasse oder einer Klasse, die von der angegebenen Klasse abgeleitet ist. `IsKindOf` mehrere unterstützt Vererbung keine oder virtuellen Basisklassen, obwohl Sie mehrfache Vererbung für Ihren abgeleiteten Klassen für die Microsoft Foundation ggf. verwenden können.  
  
 Eine Verwendungsmöglichkeit von Laufzeit Klasseninformationen wird die dynamische Erstellung von Objekten. Dieses Verfahren wird beschrieben, in dem Artikel [dynamische Objekterstellung](../mfc/dynamic-object-creation.md).  
  
 Ausführlichere Informationen zur Serialisierung und Laufzeit Klasseninformationen finden Sie in den Artikeln [Dateien in MFC](../mfc/files-in-mfc.md) und [Serialisierung](../mfc/serialization-in-mfc.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CObject](../mfc/using-cobject.md)

