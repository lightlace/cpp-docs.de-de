---
title: 'Serialisierung: Erstellen einer serialisierbaren Klasse | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- serializable class [MFC]
- DECLARE_SERIAL macro [MFC]
- default constructor [MFC]
- VERSIONABLE_SCHEMA macro [MFC]
- classes [MFC], derived
- IMPLEMENT_SERIAL macro [MFC]
- no-arguments constructor [MFC]
- Serialize method, overriding
- defaults [MFC], constructor
- CObject class [MFC], deriving serializable classes
- constructors [MFC], defining with no arguments
- serialization [MFC], serializable classes
- no default constructor
ms.assetid: 59a14d32-1cc8-4275-9829-99639beee27c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2f3824e87a2016a848b3723aaa293f235f6f9b09
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50054864"
---
# <a name="serialization-making-a-serializable-class"></a>Serialisierung: Erstellen einer serialisierbaren Klasse

Fünf Schritte sind erforderlich, um eine Klasse serialisierbar zu machen. Sie sind unten aufgeführt und in den folgenden Abschnitten beschrieben:

1. [Ableiten einer Klasse von CObject](#_core_deriving_your_class_from_cobject) (oder von einer Klasse abgeleitet `CObject`).

1. [Überschreiben die Serialize-Memberfunktion](#_core_overriding_the_serialize_member_function).

1. [Mit dem DECLARE_SERIAL-Makro](#_core_using_the_declare_serial_macro) in der Klassendeklaration.

1. [Definieren einen Konstruktor, der keine Argumente akzeptiert](#_core_defining_a_constructor_with_no_arguments).

1. [Mit dem IMPLEMENT_SERIAL-Makro in der Implementierungsdatei](#_core_using_the_implement_serial_macro_in_the_implementation_file) für die Klasse.

Aufrufen `Serialize` direkt statt über die >> und << Operatoren [CArchive](../mfc/reference/carchive-class.md), die letzten drei Schritte sind nicht für die Serialisierung erforderlich.

##  <a name="_core_deriving_your_class_from_cobject"></a> Ableiten einer Klasse von CObject

Die einfache Serialisierung-Protokoll und die Funktionen werden definiert, der `CObject` Klasse. Durch Ableiten einer Klasse von `CObject` (oder aus einer Klasse abgeleitet `CObject`), wie in der folgenden Deklaration der Klasse gezeigt `CPerson`, erhalten Sie Zugriff auf die Serialisierungsprotokoll und die Funktionalität von `CObject`.

##  <a name="_core_overriding_the_serialize_member_function"></a> Überschreiben der serialisieren Member-Funktion

Die `Serialize` Member-Funktion, die in definiert ist die `CObject` Klasse, die für die eigentliche Serialisierung zum Erfassen der aktuellen Zustand des Objekts erforderlichen Daten verantwortlich ist. Die `Serialize` Funktion verfügt über eine `CArchive` Argument, das zum Lesen und Schreiben von Daten des Objekts verwendet. Die [CArchive](../mfc/reference/carchive-class.md) Objekt verfügt über eine Memberfunktion `IsStoring`, gibt an, ob `Serialize` speichern (Schreiben von Daten) ist, oder laden (Lesen von Daten). Mit den Ergebnissen `IsStoring` als Leitfaden, Sie entweder Daten einfügen, des Objekts in der `CArchive` Objekt mit den Einfügeoperator (**<\<**) oder Extrahieren von Daten mit den Extraktionsoperator ( **>>**).

Erwägen Sie eine abgeleitete Klasse, von `CObject` und verfügt über zwei neue Membervariablen Typen `CString` und **WORD**. Das folgende Fragment des Klasse-Deklaration zeigt das neue Element aus, und die Deklaration für die überschriebene `Serialize` Memberfunktion:

[!code-cpp[NVC_MFCSerialization#1](../mfc/codesnippet/cpp/serialization-making-a-serializable-class_1.h)]

#### <a name="to-override-the-serialize-member-function"></a>Überschreiben Sie die Serialize-Member-Funktion

1. Rufen Sie die Basisklassenversion von `Serialize` um sicherzustellen, dass die geerbte Teil des Objekts serialisiert wird.

1. Fügen Sie ein oder Extrahieren Sie die Membervariablen, die spezifisch für Ihre Klasse.

   Die Operatoren zum Einfügung und Extraktion interagieren Sie mit der Archivklasse zum Lesen und Schreiben der das. Das folgende Beispiel veranschaulicht das implementieren `Serialize` für die `CPerson` Klasse deklariert wird, oben:

   [!code-cpp[NVC_MFCSerialization#2](../mfc/codesnippet/cpp/serialization-making-a-serializable-class_2.cpp)]

Sie können auch die [CArchive:: Read](../mfc/reference/carchive-class.md#read) und [CArchive::Write](../mfc/reference/carchive-class.md#write) Memberfunktionen zum Lesen und Schreiben große Mengen von nicht typisierten Daten.

##  <a name="_core_using_the_declare_serial_macro"></a> Verwenden die DECLARE_SERIAL-Makro

Die DECLARE_SERIAL-Makro ist erforderlich, in der Deklaration von Klassen, die Serialisierung unterstützt, wie hier gezeigt:

[!code-cpp[NVC_MFCSerialization#3](../mfc/codesnippet/cpp/serialization-making-a-serializable-class_3.h)]

##  <a name="_core_defining_a_constructor_with_no_arguments"></a> Definieren einen Konstruktor ohne Argumente

MFC erfordert einen standardmäßigen Konstruktor aus, wenn sie Ihre Objekte neu während der Deserialisierung (vom Datenträger geladen) erstellt. Bei der Deserialisierung werden alle Membervariablen mit den Werten, das zum Neuerstellen des Objekts erforderlich ausfüllen.

Dieser Konstruktor kann öffentlich, geschützt oder privat deklariert werden. Wenn Sie es geschützt oder privat vornehmen, können Sie sicherstellen, dass er nur von den Serialisierungsfunktionen verwendet wird. Der Konstruktor muss das Objekt in den Status versetzen, die sie bei Bedarf gelöscht werden können.

> [!NOTE]
>  Wenn Sie vergessen, einen Konstruktor ohne Argumente in einer Klasse zu definieren, die die DECLARE_SERIAL und IMPLEMENT_SERIAL-Makros verwendet, erhalten eine compilerwarnung "kein Standardkonstruktor verfügbar" in der Zeile Sie, wo die IMPLEMENT_SERIAL-Makro verwendet wird.

##  <a name="_core_using_the_implement_serial_macro_in_the_implementation_file"></a> Verwenden in der Implementierungsdatei die IMPLEMENT_SERIAL-Makro

Das IMPLEMENT_SERIAL-Makro wird verwendet, um die verschiedenen Funktionen definieren benötigt beim Ableiten einer serialisierbaren Klasse aus `CObject`. Verwenden Sie dieses Makro in der Implementierungsdatei (. CPP) für die Klasse. Die ersten beiden Argumente in das Makro gibt den Namen der Klasse und den Namen des den direkten Basisklassen.

Das dritte Argument für dieses Makro wird eine Reihe von Schemas. Die Schema-Anzahl ist im Wesentlichen eine Versionsnummer für Objekte der Klasse. Verwenden Sie eine ganze Zahl größer als oder gleich 0, für die Schema-Anzahl. (Verwechseln Sie nicht diese Zahl Schema mit der datenbankterminologie.)

Der MFC-Serialisierungscode überprüft die Schema-Anzahl, beim Lesen von Objekten in den Arbeitsspeicher. Wenn die Anzahl der Schema des Objekts auf dem Datenträger die Anzahl von Schema für die Klasse im Arbeitsspeicher nicht übereinstimmt, löst die Bibliothek eine `CArchiveException`, verhindert, dass das Programm eine falsche Version des Objekts zu lesen.

Wenn Sie möchten Ihre `Serialize` Memberfunktion versucht, mehrere Versionen lesen können – d. h. Dateien, die mit verschiedenen Versionen der Anwendung geschrieben – können Sie den Wert *VERSIONABLE_SCHEMA* als Argument an die IMPLEMENT_SERIAL -Makro. Weitere Informationen zur Verwendung und ein Beispiel finden Sie unter den `GetObjectSchema` Memberfunktion der Klasse `CArchive`.

Das folgende Beispiel zeigt, wie für eine Klasse, die mit IMPLEMENT_SERIAL `CPerson`, d. h. abgeleitet `CObject`:

[!code-cpp[NVC_MFCSerialization#4](../mfc/codesnippet/cpp/serialization-making-a-serializable-class_4.cpp)]

Nachdem Sie eine serialisierbare Klasse haben, können Sie Objekte der Klasse serialisieren, wie im folgenden Artikel beschrieben [Serialisierung: Serialisieren eines Objekts](../mfc/serialization-serializing-an-object.md).

## <a name="see-also"></a>Siehe auch

[Serialisierung](../mfc/serialization-in-mfc.md)

