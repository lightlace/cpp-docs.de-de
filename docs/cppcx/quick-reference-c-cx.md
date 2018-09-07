---
title: Kurzreferenz (C++ / CX) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: ba457195-26e5-43aa-b99d-24a871e550f4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5b3ee46b2be08992fa3254edfbf2423b80dcabb1
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44102116"
---
# <a name="quick-reference-ccx"></a>Kurzreferenz (C++/CX)

Die Windows-Runtime unterstützt apps für universelle Windows-Plattform (UWP), die nur in einer vertrauenswürdigen betriebssystemumgebung ausgeführt und verwenden autorisierte Funktionen, Datentypen und Geräte über den Microsoft Store verteilt werden. C++ / CX vereinfacht das Schreiben von apps für die Windows-Runtime. In diesem Artikel ist eine kurze Übersicht. eine umfassendere Dokumentation finden Sie unter [Typsystem](../cppcx/type-system-c-cx.md).

Wenn Sie in der Befehlszeile erstellen, verwenden die **/Zw** -Compileroption verwenden, um eine UWP-app oder Komponente für Windows-Runtime zu erstellen. Geben Sie für Windows-Runtime-Deklarationen, die in den Windows-Runtime-Metadatendatei (.winmd)-Dateien definiert sind den Zugriff auf, die `#using` Richtlinie oder die **/FU** -Compileroption. Wenn Sie ein Projekt für eine UWP-app erstellen, wird Visual Studio standardmäßig legt diese fest und fügt Verweise auf alle Windows-Runtime-Bibliotheken hinzu.

## <a name="quick-reference"></a>Kurzreferenz

|Konzept|Standard C++|C++/CX|Hinweise|
|-------------|--------------------|------------------------------------------------------------------|-------------|
|Grundlegende Typen|Grundlegende C++-Typen|C++ / CX-grundlegenden Typen, die grundlegende Typen implementieren, die in der Windows-Runtime definiert sind.|Die `default` -Namespace enthält C++ / CX-integrierte grundlegende Typen. Ordnet der Compiler implizit die C++ / CX-Basistypen zu Standard-c++-Typen.<br /><br /> Die `Platform` -Familie von Namespaces enthält Typen, die grundlegende Windows-Runtime-Typen implementieren.|
||`bool`|`bool`|Ein 8-Bit-boolescher Wert.|
||`__wchar_t`|`char16`|Ein nicht numerischer 16-Bit-Wert, der einen Unicode-Codepunkt (UTF-16) darstellt.|
||`short`<br /><br /> `unsigned short`|`int16`<br /><br /> `uint16`|Eine 16-Bit-Ganzzahl mit Vorzeichen.<br /><br /> Eine 16-Bit-Ganzzahl ohne Vorzeichen.|
||`int`<br /><br /> `unsigned int`|`int`<br /><br /> `uint32`|Eine 32-Bit-Ganzzahl mit Vorzeichen.<br /><br /> Eine 32-Bit-Ganzzahl ohne Vorzeichen.|
||`long long` - oder - `__int64`<br /><br /> `unsigned long long`|`int64`<br /><br /> `uint64`|Eine 64-Bit-Ganzzahl mit Vorzeichen.<br /><br /> Eine 64-Bit-Ganzzahl ohne Vorzeichen.|
||`float, double`|`float32, float64`|Eine 32-Bit- oder 64-Bit-IEEE 754-Gleitkommazahl.|
||`enum {}`|`enum class {}`<br /><br /> - oder - <br /><br /> `enum struct {}`|Eine 32-Bit-Enumeration.|
||(Trifft nicht zu)|`Platform::Guid`|Ein nicht numerischer 128-Bit-Wert (eine GUID) im `Platform` -Namespace.|
||`std::time_get`|`Windows::Foundation::DateTime`|Eine Datum/Uhrzeit-Struktur.|
||(Trifft nicht zu)|`Windows::Foundation::TimeSpan`|Eine TimeSpan-Struktur.|
||(Trifft nicht zu)|`Platform::Object^`|Der Verweis gezählte Basisobjekt in der C++-Ansicht von der Windows-Runtime-Typsystem.|
||`std::wstring`<br /><br /> `L"..."`|`Platform::String^`|`Platform::String^` ist eine nach Verweis gezählte, unveränderliche Sequenz von Unicode-Zeichen, die Text darstellt.|
|Zeiger|Zeiger auf Objekt (`*`):<br /><br /> `std::shared_ptr`|Handle-to-object (`^`, steht für Caretzeichen):<br /><br /> *T^ identifier*|Alle Windows-Runtime-Klassen werden mit dem Handle-to-Object-Modifizierer deklariert. Auf Member des Objekts wird mit dem Klassenmemberzugriffs-Operator Pfeil (`->`) zugegriffen.<br /><br /> Die Hat-Modifizierer bedeutet "Zeiger auf ein Windows-Runtime-Objekt, das automatisch Verweis gezählt." Genauer gesagt, deklariert "handle-to-object", dass der Compiler Code einfügen soll, um den Verweiszählerwert des Objekts automatisch zu verwalten und das Objekt zu löschen, wenn der Verweiszähler Null ist.|
|Referenz|Ein Verweis auf ein Objekt (`&`):<br /><br /> *T* `&` *identifier*|Nachverfolgungsverweis (`%`):<br /><br /> *T* `%` *identifier*|Nur Windows-Runtime, die Typen deklariert werden können, mit dem Modifizierer zu verweisen. Auf Member des Objekts wird mit dem Klassenmemberzugriffs-Operator Punkt (`.`) zugegriffen.<br /><br /> Der Nachverfolgungsverweis bedeutet "einen Verweis auf ein Windows-Runtime-Objekt, das automatisch einen Verweiszähler." Genauer gesagt, deklariert ein Nachverfolgungsverweis, dass der Compiler Code einfügen soll, um den Verweiszählerwert des Objekts automatisch zu verwalten und das Objekt zu löschen, wenn der Verweiszähler Null ist.|
|Dynamische Typdeklaration|`new`|`ref new`|Ordnet ein Windows-Runtime-Objekt, und klicken Sie dann auf dieses Objekt gibt ein Handle zurück.|
|Verwaltung der Objektlebensdauer|`delete` *identifier*<br /><br /> `delete[]`  *identifier*|(Destruktoraufruf.)|Die Lebensdauer wird durch Verweiszählung bestimmt. Ein Löschaufruf startet den Destruktor und gibt selbst keinen Speicherplatz frei.|
|Arraydeklaration|*T  identifier* `[]`<br /><br /> `std::array` *identifier*|`Array<` *T* `^>^` *identifier* `(` *size* `)`<br /><br /> - oder - <br /><br /> `WriteOnlyArray<` *T* `^>`  *identifier* `(` *size* `)`|Deklariert ein eindimensionales bearbeitbares oder schreibgeschütztes Array vom Typ T^. Das Array selbst ist auch ein nach Verweis gezähltes Objekt, das mit dem handle-to-object-Modifizierer deklariert werden muss.<br /><br /> (Arraydeklarationen verwenden eine Vorlagenheaderklasse, die im `Platform` -Namespace ist.)|
|Klassendeklaration|`class`  *identifier* `{}`<br /><br /> `struct` *identifier* `{}`|`ref class` *identifier* `{}`<br /><br /> `ref struct` *identifier* `{}`|Deklariert eine Laufzeitklasse mit privater Standardbarrierefreiheit.<br /><br /> Deklariert eine Laufzeitklasse mit öffentlicher Standardbarrierefreiheit.|
|Strukturdeklaration|`struct` *identifier* `{}`<br /><br /> (d. h. eine POD-Struktur (Plain Old Data))|`value class` *identifier* `{}`<br /><br /> `value struct` *identifier* `{}`|Deklariert eine POD-Struktur mit privater Standardbarrierefreiheit.<br /><br /> Eine Wertklasse kann in Windows-Metadaten dargestellt werden, eine Standard-C++-Klasse hingegen nicht.<br /><br /> Deklariert eine POD-Struktur mit öffentlicher Standardbarrierefreiheit.<br /><br /> Eine Wertstruktur kann in Windows-Metadaten dargestellt werden, eine Standard-C++-Struktur hingegen nicht.|
|Schnittstellendeklaration|Abstrakte Klasse, die nur rein virtuelle Funktionen enthält.|`interface class` *identifier* `{}`<br /><br /> `interface struct` *identifier* `{}`|Deklariert eine Schnittstelle mit privater Standardbarrierefreiheit.<br /><br /> Deklariert eine Schnittstelle mit öffentlicher Standardbarrierefreiheit.|
|delegate|`std::function`|`public delegate` *Rückgabetyp* *delegate-type-identifier* `(` *[Parameter]* `);`|Deklariert ein Objekt, das wie ein Funktionsaufruf aufgerufen werden kann.|
|event|(Trifft nicht zu)|`event` *delegate-type-identifier* *event-identifier* `;`<br /><br /> *delegate-type-identifier* *delegate-identifier* = `ref new`*delegate-type-identifier*`( this`*[, Parameter]*`);`<br /><br /> *event-identifier* `+=` *delegate-identifier* `;`<br /><br /> - oder - <br /><br /> `EventRegistrationToken` *token-identifier* = *obj*`.`*event-identifier*`+=`*delegate-identifier*`;`<br /><br /> - oder - <br /><br /> `auto` *Token-Identifier* = *Obj*. *Ereignis-ID*`::add(`*Delegat-ID*`);`<br /><br /> *obj* `.` *event-identifier* `-=` *token-identifier* `;`<br /><br /> - oder - <br /><br /> *obj* `.` *event-identifier* `::remove(` *token-identifier* `);`|Deklariert ein Ereignisobjekt, das eine Ereignishandlerauflistung (Delegaten) speichert, die beim Auftreten eines Ereignisses aufgerufen wird.<br /><br /> Erstellt einen Ereignishandler.<br /><br /> Fügt einen Ereignishandler hinzu.<br /><br /> Wenn ein Ereignishandler hinzugefügt wird, wird ein Ereignistoken (*token-identifier*) zurückgegeben. Falls Sie den Ereignishandler explizit entfernen möchten, müssen Sie das Ereignistoken für die spätere Verwendung speichern.<br /><br /> Entfernt einen Ereignishandler.<br /><br /> Um einen Ereignishandler zu entfernen, müssen Sie das Ereignistoken angeben, das Sie beim Hinzufügen des Ereignishandlers gespeichert haben.|
|property|(Trifft nicht zu)|`property` *T* *identifier*;<br /><br /> `property` *T* *identifier* `[` *Index* `];`<br /><br /> `property` *T* `default[` *Index* `];`|Deklariert, dass auf eine Klassen- oder eine Objektmemberfunktion mit derselben Syntax zugegriffen wird, die für den Zugriff auf einen Datenmember oder ein indiziertes Arrayelement verwendet wurde.<br /><br /> Deklariert eine Eigenschaft in einer Klassen- oder Objektmemberfunktion.<br /><br /> Deklariert eine indizierte Eigenschaft in einer Objektmemberfunktion.<br /><br /> Deklariert eine indizierte Eigenschaft in einer Klassenmemberfunktion.|
|Parametrisierte Typen|Vorlagen|`generic <typename` *T* `> interface class` *identifier* `{}`<br /><br /> `generic <typename` *T* `> delegate` *[Rückgabetyp]* *delegate-identifier* `() {}`|Deklariert eine parametrisierte Schnittstellenklasse.<br /><br /> Deklariert einen parametrisierten Delegaten.|
|Auf NULL festlegbare Werttypen|`boost::optional<T>`|[Platform:: ibox \<T >](../cppcx/platform-ibox-interface.md)|Ermöglicht, dass Variablen von skalaren Typen und Wertstrukturen einen Wert von `nullptr`aufweisen.|

## <a name="see-also"></a>Siehe auch

[Sprachreferenz zu Visual C++](../cppcx/visual-c-language-reference-c-cx.md)