---
title: 'Serialisierung: Erstellen einer serialisierbaren Klasse | Microsoft Docs'
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
ms.openlocfilehash: 4412e8db861ac522c0f1b1d7192bfbb83612d64c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33383415"
---
# <a name="serialization-making-a-serializable-class"></a>Serialisierung: Erstellen einer serialisierbaren Klasse
Fünf wichtige Schritte sind erforderlich, um eine Klasse serialisierbar zu machen. Sie sind unten aufgeführt und in den folgenden Abschnitten erläutert:  
  
1.  [Ableiten einer Klasse von CObject](#_core_deriving_your_class_from_cobject) (oder von einer Klasse abgeleitet `CObject`).  
  
2.  [Überschreiben die Memberfunktion Serialize](#_core_overriding_the_serialize_member_function).  
  
3.  [DECLARE_SERIAL-Makro mit](#_core_using_the_declare_serial_macro) in der Klassendeklaration.  
  
4.  [Definieren einen Konstruktor, der keine Argumente akzeptiert](#_core_defining_a_constructor_with_no_arguments).  
  
5.  [Verwenden das IMPLEMENT_SERIAL-Makro in der Implementierungsdatei](#_core_using_the_implement_serial_macro_in_the_implementation_file) für die Klasse.  
  
 Beim Aufrufen `Serialize` direkt Umweg über den >> und <<-Operatoren [CArchive](../mfc/reference/carchive-class.md), die letzten drei Schritte sind nicht erforderlich, für die Serialisierung.  
  
##  <a name="_core_deriving_your_class_from_cobject"></a> Ableiten einer Klasse von CObject  
 Die einfache Serialisierung-Protokoll und die Funktionen sind in definiert die `CObject` Klasse. Durch Ableiten einer Klasse von `CObject` (oder von einer Klasse abgeleitet `CObject`), wie in der folgenden Deklaration der Klasse gezeigt `CPerson`, erhalten Sie Zugriff auf die Serialisierungsprotokoll und die Funktionalität des `CObject`.  
  
##  <a name="_core_overriding_the_serialize_member_function"></a> Überschreiben der Memberfunktion serialisieren  
 Die `Serialize` Memberfunktion ist, definiert in der `CObject` Klasse, die für die eigentliche Serialisierung zum Erfassen der aktuelle Status des Objekts erforderlichen Daten verantwortlich ist. Die `Serialize` Funktion verfügt über eine `CArchive` Argument, das zum Lesen und Schreiben der Objektdaten verwendet. Die [CArchive](../mfc/reference/carchive-class.md) Objekt verfügt über eine Memberfunktion `IsStoring`, gibt an, ob `Serialize` (das Schreiben von Daten) speichern oder laden (Lesen von Daten). Anhand der Ergebnisse `IsStoring` als Leitfaden, Sie entweder Daten einfügen, des Objekts in der `CArchive` Objekt mit dem Operator zum Einfügen (**<\<**) oder Extrahieren von Daten mit den Extraktionsoperator ( **>>**).  
  
 Betrachten Sie eine Klasse, die abgeleitet ist `CObject` und verfügt über zwei neue Membervariablen Typen `CString` und **WORD**. Die folgende Klasse Deklaration Fragment zeigt das neue Element, Variablen und die Deklaration für die überschriebene `Serialize` Memberfunktion:  
  
 [!code-cpp[NVC_MFCSerialization#1](../mfc/codesnippet/cpp/serialization-making-a-serializable-class_1.h)]  
  
#### <a name="to-override-the-serialize-member-function"></a>Serialize-Memberfunktion überschreiben  
  
1.  Rufen Sie die Basisklassenversion von `Serialize` um sicherzustellen, dass die geerbte Teil des Objekts serialisiert wird.  
  
2.  Stecken extrahieren Sie die spezifisch für Ihre Klasse Membervariablen zu.  
  
     Die Einfügung und Extraktion Operatoren mit der Archivklasse zum Lesen und schreiben die Daten interagieren. Das folgende Beispiel veranschaulicht das implementieren `Serialize` für die `CPerson` Klasse oben deklariert:  
  
     [!code-cpp[NVC_MFCSerialization#2](../mfc/codesnippet/cpp/serialization-making-a-serializable-class_2.cpp)]  
  
 Sie können auch die [CArchive:: Read](../mfc/reference/carchive-class.md#read) und [CArchive::Write](../mfc/reference/carchive-class.md#write) Memberfunktionen zum Lesen und Schreiben von großen Datenmengen nicht typisierte Daten.  
  
##  <a name="_core_using_the_declare_serial_macro"></a> Verwenden Sie das DECLARE_SERIAL-Makro  
 Die `DECLARE_SERIAL` Makro muss in der Deklaration von Klassen, die Serialisierung unterstützen, wie hier gezeigt:  
  
 [!code-cpp[NVC_MFCSerialization#3](../mfc/codesnippet/cpp/serialization-making-a-serializable-class_3.h)]  
  
##  <a name="_core_defining_a_constructor_with_no_arguments"></a> Definieren eines Konstruktors ohne Argumente  
 MFC erfordert einen Standardkonstruktor, wenn sie die Objekte neu während der Deserialisierung (geladen vom Datenträger) erstellt. Bei der Deserialisierung werden alle Membervariablen mit den Werten, die zum Neuerstellen des Objekts erforderlich ausgefüllt.  
  
 Dieser Konstruktor kann öffentlich, geschützt oder privat deklariert werden. Wenn Sie geschützt oder privat zu vereinfachen, können Sie sicherstellen, dass er nur von den Serialisierungsfunktionen verwendet wird. Der Konstruktor muss das Objekt in einen Zustand versetzt, die sie bei Bedarf gelöscht werden können.  
  
> [!NOTE]
>  Wenn Sie vergessen, einen Konstruktor ohne Argumente in einer Klasse zu definieren, verwendet der `DECLARE_SERIAL` und `IMPLEMENT_SERIAL` Makros, erhalten Sie eine compilerwarnung "kein Standardkonstruktor verfügbar" in der Zeile, in dem die `IMPLEMENT_SERIAL` Makro wird verwendet.  
  
##  <a name="_core_using_the_implement_serial_macro_in_the_implementation_file"></a> Verwenden in der Implementierungsdatei IMPLEMENT_SERIAL-Makro  
 Die `IMPLEMENT_SERIAL` Makro wird verwendet, um die verschiedenen Funktionen definieren benötigt beim Ableiten einer serialisierbaren Klasse aus `CObject`. Verwenden Sie dieses Makro in der Implementierungsdatei (. CPP) für die Klasse. Die ersten beiden Argumente für das Makro sind der Name der Klasse und den Namen der unmittelbaren Basisklasse.  
  
 Das dritte Argument dieses Makro ist eine Schema-Zahl. Die Schema-Anzahl ist im Wesentlichen eine Versionsnummer für Objekte der Klasse. Verwenden Sie eine ganze Zahl größer als oder gleich 0, für die Schemanummer. (Verwechseln Sie nicht diese Zahl Schema mit der Terminologie von Datenbanken.)  
  
 MFC-Serialisierungscode überprüft die Schema-Anzahl, wenn Objekte in den Arbeitsspeicher gelesen. Wenn die Anzahl von Schema für das Objekt auf dem Datenträger die Anzahl von Schema für die Klasse im Arbeitsspeicher nicht übereinstimmt, löst die Bibliothek eine `CArchiveException`, verhindert, dass das Programm eine falsche Version des Objekts lesen.  
  
 Wenn Sie möchten Ihre `Serialize` Memberfunktion in der Lage, mehrere Versionen zu lesen sein –, also Dateien mit unterschiedlichen Versionen der Anwendung geschrieben – können Sie den Wert **VERSIONABLE_SCHEMA** als Argument an die `IMPLEMENT_SERIAL` Makro. Weitere Informationen zur Verwendung und ein Beispiel finden Sie unter der `GetObjectSchema` Memberfunktion der Klasse `CArchive`.  
  
 Das folgende Beispiel zeigt, wie Sie `IMPLEMENT_SERIAL` für eine Klasse `CPerson`, d. h. abgeleitet `CObject`:  
  
 [!code-cpp[NVC_MFCSerialization#4](../mfc/codesnippet/cpp/serialization-making-a-serializable-class_4.cpp)]  
  
 Nachdem Sie eine serialisierbare Klasse haben, können Sie Objekte der Klasse, serialisieren, wie im Artikel erläutert [Serialisierung: Serialisieren eines Objekts](../mfc/serialization-serializing-an-object.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Serialisierung](../mfc/serialization-in-mfc.md)

