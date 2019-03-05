---
title: Zwei Möglichkeiten zur Erstellung eines CArchive-Objekts
ms.date: 11/04/2016
f1_keywords:
- CArchive
helpviewer_keywords:
- CArchive class [MFC], closing CArchive objects
- CArchive objects [MFC], closing
- I/O [MFC], creating CArchive objects
- serialization [MFC], CArchive class
- CArchive objects [MFC]
- storage [MFC], CArchive class [MFC]
- data storage [MFC], CArchive class
- CArchive class [MFC], constructor
ms.assetid: aefa28ce-b55c-40dc-9e42-5f038030985d
ms.openlocfilehash: 80e3e73840bce53691c3f5fdafb62c60bdb8f832
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57273802"
---
# <a name="two-ways-to-create-a-carchive-object"></a>Zwei Möglichkeiten zur Erstellung eines CArchive-Objekts

Es gibt zwei Möglichkeiten zum Erstellen einer `CArchive` Objekt:

- [Implizite Erstellung eines CArchive-Objekts über das framework](#_core_implicit_creation_of_a_carchive_object_via_the_framework)

- [Explizite Erstellung eines CArchive-Objekts](#_core_explicit_creation_of_a_carchive_object)

##  <a name="_core_implicit_creation_of_a_carchive_object_via_the_framework"></a> Implizite Erstellung eines CArchive-Objekts über das Framework

Die meisten allgemeinen und am einfachsten, besteht darin, das Framework erstellen können eine `CArchive` Objekt für das Dokument für das Speichern, speichern und öffnen-Befehle im Menü Datei.

Hier ist, was das Framework ermöglicht wird, wenn der Benutzer Ihrer Anwendung den Befehl "Speichern unter" aus dem Menü "Datei" ausgibt:

1. Stellt die **speichern** Dialogfeld und ruft den Dateinamen vom Benutzer ab.

1. Öffnet die Datei mit dem Namen der Benutzer als ein `CFile` Objekt.

1. Erstellt eine `CArchive` Objekt, das dieser verweist `CFile` Objekt. Bei der Erstellung der `CArchive` Objekt, das Framework wird der Modus auf "Speichern" (schreiben, zu serialisieren), im Gegensatz zu "laden" (Lesen, zu deserialisieren).

1. Ruft die `Serialize` in definierte Funktion Ihrer `CDocument`-abgeleitete Klasse sein, und übergeben sie einen Verweis auf die `CArchive` Objekt.

Des Dokuments `Serialize` Funktion schreibt dann die Daten in die `CArchive` -Objekts, wie in Kürze erläutert. Nach der Rückkehr aus Ihrer `Serialize` -Funktion, um das Framework zerstört die `CArchive` Objekt und klicken Sie dann die `CFile` Objekt.

Daher, wenn Sie das Framework erstellen können die `CArchive` Objekt für das Dokument, müssen Sie lediglich Implementieren des Dokuments `Serialize` -Funktion, die schreibt und liest in und aus dem Archiv. Müssen Sie auch implementieren `Serialize` für alle `CObject`-abgeleiteten Objekte aus, die des Dokuments `Serialize` Funktion wird dann serialisiert, direkt oder indirekt.

##  <a name="_core_explicit_creation_of_a_carchive_object"></a> Explizite Erstellung eines CArchive-Objekts

Neben dem Serialisieren ein Dokument über das Framework, stehen die anderen Situationen, wenn Sie ggf. eine `CArchive` Objekt. Sie können beispielsweise zum Serialisieren von Daten in und aus der Zwischenablage, dargestellt durch eine `CSharedFile` Objekt. Oder, empfiehlt es sich um eine Benutzeroberfläche zum Speichern einer Datei, die sich von dem vom Framework bereitgestellt wird. In diesem Fall können Sie explizit erstellen eine `CArchive` Objekt. Dazu die gleiche Weise wie, die das Framework der Fall ist, die verwenden Sie das folgende Verfahren.

#### <a name="to-explicitly-create-a-carchive-object"></a>Ein CArchive-Objekt explizit zu erstellen.

1. Erstellen einer `CFile` Objekt oder ein Objekt abgeleitet `CFile`.

1. Übergeben Sie die `CFile` Objekt an den Konstruktor für `CArchive`, wie im folgenden Beispiel gezeigt:

   [!code-cpp[NVC_MFCSerialization#5](../mfc/codesnippet/cpp/two-ways-to-create-a-carchive-object_1.cpp)]

   Das zweite Argument für die `CArchive` Konstruktor ist ein Enumerationswert, der angibt, ob das Archiv für das Speichern oder Laden von Daten in oder aus der Datei verwendet wird. Die `Serialize` Funktion eines Objekts überprüft, ob dieser Zustand durch Aufrufen der `IsStoring` -Funktion für das Archivobjekt.

Wenn Sie fertig sind, speichern oder Laden von Daten in oder aus sind die `CArchive` Objekt, schließen Sie sie. Obwohl die `CArchive` (und `CFile`) Objekte werden automatisch geschlossen, das Archiv (und Datei), es wird empfohlen, die explizit ist, da die Wiederherstellung nach Fehlern erleichtert. Weitere Informationen zur Fehlerbehandlung finden Sie im Artikel [Ausnahmen: Abfangen und Löschen von Ausnahmen](../mfc/exceptions-catching-and-deleting-exceptions.md).

#### <a name="to-close-the-carchive-object"></a>Um die CArchive-Objekt zu schließen.

1. Das folgende Beispiel veranschaulicht, wie Sie schließen die `CArchive` Objekt:

   [!code-cpp[NVC_MFCSerialization#6](../mfc/codesnippet/cpp/two-ways-to-create-a-carchive-object_2.cpp)]

## <a name="see-also"></a>Siehe auch

[Serialisierung: Serialisieren eines Objekts](../mfc/serialization-serializing-an-object.md)
