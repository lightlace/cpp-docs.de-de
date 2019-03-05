---
title: Zugreifen auf Laufzeit-Klasseninformationen
ms.date: 11/04/2016
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
ms.openlocfilehash: 2e4f8685033fc7a8a2f49dafa7ef4e4e019d8989
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57298827"
---
# <a name="accessing-run-time-class-information"></a>Zugreifen auf Laufzeit-Klasseninformationen

In diesem Artikel wird erläutert, wie auf Informationen zu der Klasse eines Objekts zur Laufzeit zugegriffen wird.

> [!NOTE]
>  MFC verwendet nicht die [Laufzeit-Typeninformation](../cpp/run-time-type-information.md) (RTTI)-Unterstützung in Visual C++ 4.0 eingeführt wurden.

Wenn Sie eine Klasse von abgeleitet haben [CObject](../mfc/reference/cobject-class.md) und verwendet die **DECLARE**_**dynamische** und `IMPLEMENT_DYNAMIC`, `DECLARE_DYNCREATE` und `IMPLEMENT_DYNCREATE`, oder die `DECLARE_SERIAL` und `IMPLEMENT_SERIAL` Makros in diesem Artikel erläutert [Ableiten einer Klasse von CObject](../mfc/deriving-a-class-from-cobject.md), `CObject` -Klasse verfügt über die Möglichkeit, die exakte Klasse eines Objekts zur Laufzeit zu bestimmen.

Diese Funktion ist besonders hilfreich, wenn zusätzlichen typüberprüfung von Funktionsargumenten erforderlich ist und Sie, speziellen Code basierend auf der Klasse eines Objekts schreiben müssen. Diese Vorgehensweise ist jedoch in der Regel nicht empfohlen, da es die Funktionalität von virtuellen Funktionen dupliziert.

Die `CObject` Memberfunktion `IsKindOf` können verwendet werden, um festzustellen, ob ein bestimmtes Objekt zu einer bestimmten Klasse gehört, oder wenn es von einer bestimmten Klasse abgeleitet ist. Das Argument für `IsKindOf` ist eine `CRuntimeClass` -Objekt, das Sie mit der `RUNTIME_CLASS` Makro mit dem Namen der Klasse.

### <a name="to-use-the-runtimeclass-macro"></a>Verwenden Sie die vom RUNTIME_CLASS-Makro

1. Verwendung `RUNTIME_CLASS` mit dem Namen der Klasse, wie hier gezeigt für die Klasse `CObject`:

   [!code-cpp[NVC_MFCCObjectSample#4](../mfc/codesnippet/cpp/accessing-run-time-class-information_1.cpp)]

Sie müssen nur selten direkt auf das Objekt für die Run-Time-Klasse zugreifen. Eine weitere häufige Verwendung ist das Laufzeitklasse-Objekt, das Übergeben der `IsKindOf` Funktion, wie in der nächsten Prozedur gezeigt. Die `IsKindOf` Funktion testet ein Objekt, um festzustellen, ob sie zu einer bestimmten Klasse gehört.

#### <a name="to-use-the-iskindof-function"></a>Verwenden die IsKindOf-Funktion

1. Stellen Sie sicher, dass die Klasse Laufzeitklasse Unterstützung verfügt. Also die Klasse muss abgeleitet sein direkt oder indirekt von `CObject` und verwendet die **DECLARE**_**dynamische** und `IMPLEMENT_DYNAMIC`, `DECLARE_DYNCREATE` und `IMPLEMENT_DYNCREATE`, oder die `DECLARE_SERIAL` und `IMPLEMENT_SERIAL` Makros in diesem Artikel erläutert [Ableiten einer Klasse von CObject](../mfc/deriving-a-class-from-cobject.md).

1. Rufen Sie die `IsKindOf` Member-Funktion für Objekte dieser Klasse mithilfe der `RUNTIME_CLASS` Makro zum Generieren der `CRuntimeClass` -Arguments zu, wie hier gezeigt:

   [!code-cpp[NVC_MFCCObjectSample#2](../mfc/codesnippet/cpp/accessing-run-time-class-information_2.h)]

   [!code-cpp[NVC_MFCCObjectSample#5](../mfc/codesnippet/cpp/accessing-run-time-class-information_3.cpp)]

    > [!NOTE]
    >  IsKindOf gibt **"true"** Wenn das Objekt ein Member der angegebenen Klasse oder einer Klasse, die von der angegebenen Klasse abgeleitet ist. `IsKindOf` unterstützt mehrere vererbungs- oder virtuelle Basisklassen nicht zwar mehrfache Vererbung für Ihren abgeleiteten Klassen für die Microsoft Foundation bei Bedarf verwendet werden können.

Eine Verwendung der Laufzeit Klasseninformationen ist in der dynamischen Erstellung von Objekten. Dieser Prozess wird in diesem Artikel erläuterten [dynamische Objekterstellung](../mfc/dynamic-object-creation.md).

Ausführlichere Informationen zur Serialisierung und Laufzeit Klasseninformationen, finden Sie unter den Artikeln [Dateien in MFC](../mfc/files-in-mfc.md) und [Serialisierung](../mfc/serialization-in-mfc.md).

## <a name="see-also"></a>Siehe auch

[Verwenden von CObject](../mfc/using-cobject.md)
