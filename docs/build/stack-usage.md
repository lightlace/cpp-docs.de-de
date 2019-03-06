---
title: X64 stack-Nutzung
ms.date: 12/17/2018
ms.assetid: 383f0072-0438-489f-8829-cca89582408c
ms.openlocfilehash: 902e4304ac124be46c6edf0860118dc522b34890
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57425600"
---
# <a name="x64-stack-usage"></a>X64 stack-Nutzung

Alle Speicher außerhalb der aktuellen Adresse der RSP flüchtige gilt: Das Betriebssystem und einen Debugger, kann dieser Arbeitsspeicher während einer Debugsitzung für Benutzer oder einem Interrupthandler überschreiben. RSP muss daher immer festgelegt werden, bevor Sie versuchen, das Lesen und Schreiben von Werten in einen Stapelrahmen.

Dieser Abschnitt beschreibt die Zuordnung an Stapelspeicher für lokale Variablen und die **Alloca** systeminterne.

## <a name="stack-allocation"></a>Stapelreservierung

Der Prolog einer Funktion ist verantwortlich für die Zuordnung der Stapelspeicher für lokale Variablen, Stapelparameter gespeicherte Register, und registrieren Sie die Parameter.

Der Eingabeaufforderungsbereich für Parameter ist immer am unteren Rand im Stapel (auch wenn `alloca` dient), sodass er immer an die Rücksendeadresse angrenzende bei einem beliebigen Funktionsaufruf kann. Mindestens vier Einträge enthält, aber immer ausreichend Speicherplatz für alle Parameter benötigt, von jeder Funktion, die aufgerufen werden kann. Beachten Sie, dass immer Speicherplatz für die Registerparameter, zugewiesen ist, selbst wenn die die Parametern selbst nie auf den Stapel befinden; eine aufgerufene Funktion ist garantiert, dass Speicherplatz für alle seine Parameter zugeordnet wurde. Privatadressen sind für die Registerargumente erforderlich, damit ein zusammenhängender Bereich verfügbar ist, für den Fall, dass die aufgerufene Funktion die Adresse der Argumentliste (Va_list) oder ein einzelnes Argument verwenden muss. Dieser Bereich bietet auch einen praktischer Ort für die Registerargumente während der Ausführung der Thunk sowie eine Option für das Debuggen zu speichern (z. B. die Argumente auf einfache Weise zu suchen, die während des Debuggens, wenn sie an ihrer Basisadresse im Prologcode gespeichert sind). Auch wenn die aufgerufene Funktion über weniger als 4 Parameter verfügt, diese 4-Stack-Standorte gehören effektiv von der aufgerufenen Funktion und können von der aufgerufenen Funktion für andere Zwecke neben Speichern verwendet werden.  Der Aufrufer kann daher keine Informationen in dieser Region des Stapels über einen Funktionsaufruf hinweg speichern.

Wenn Speicherplatz dynamisch belegt wird (`alloca`) in einer Funktion klicken Sie dann ein nicht flüchtiges Register muss verwendet werden als Frame-Pointer auf um die Basis der fester Bestandteil des Stapels zu markieren und, bei der Registrierung gespeichert werden muss, und im Prolog initialisiert. Hinweis: Wenn `alloca` wird verwendet, Aufrufe an den gleichen aufgerufenen vom gleichen Aufrufer möglicherweise unterschiedliche Basisadressen für ihre Registrierung-Parameter.

Der Stapel werden immer 16-Byte-beibehalten, außer im Prolog (z. B., nachdem die Rückgabeadresse mithilfe von Push übertragen wird) und mit Ausnahme der wie angegeben in [Funktionstypen](#function-types) für eine bestimmte Klasse von Frame-Funktionen.

Im folgenden finden, dass ein Beispiel für die where-Funktionsaufrufe ein ein innerer Prolog der Funktion Funktion Stapellayout bereits Speicherplatz für alle Register und Stack erforderlichen Parameter B am unteren Rand der Stapel reserviert hat. Der Aufruf wird die Rückgabeadresse und B Prolog reserviert Speicherplatz für die zugehörigen lokalen Variablen, nicht flüchtigen Register und des erforderlichen Speicherplatzes für Funktionen aufrufen. Wenn B verwendet `alloca`, der Speicherplatz wird zwischen der lokalen Variable/permanenten Register und den Eingabeaufforderungsbereich für Parameter Stapel zugeordnet.

![AMD-Konvertierungsbeispiel](../build/media/vcamd_conv_ex_5.png "AMD-Konvertierungsbeispiel")

Wenn die Funktion B eine andere Funktion aufruft, wird die Absenderadresse für RCX direkt unterhalb der Privatadresse abgelegt.

## <a name="dynamic-parameter-stack-area-construction"></a>Dynamische Parameterstapelbereichskonstruktion

Wenn der Frame-Pointer verwendet wird, ist die Option zum dynamischen Erstellen von den Eingabeaufforderungsbereich für Parameter Stapel vorhanden. Dies derzeit erfolgt nicht in der X64 Compiler.

## <a name="function-types"></a>Funktionstypen

Es gibt im Grunde zwei Arten von Funktionen. Wird aufgerufen, eine Funktion, die einen Stapelrahmen erfordert eine *frame-Funktion*. Wird aufgerufen, eine Funktion, die nicht über einen Stapelrahmen erfordert eine *untergeordnete Funktion*.

Eine Frame-Funktion ist eine Funktion, die Stapelspeicher zuweist, andere Funktionen aufruft, nicht flüchtigen Register gespeichert oder mithilfe der Ausnahmebehandlung. Darüber hinaus wird die Funktionstabelleneintrag erforderlich. Eine Frame-Funktion muss einen Prolog und einen Epilog. Eine Funktion des Frames Stapelspeicher kann dynamisch zuordnen und Frame-Pointer nutzen kann. Eine Frame-Funktion verfügt über den vollständigen Funktionsumfang dieses aufrufen, bei denen standard.

Wenn eine Frame-Funktion nicht eine andere Funktion aufruft, muss es ist nicht erforderlich, um den Stapel auszurichten (Siehe den Abschnitt [Stapelreservierung](#stack-allocation)).

Eine Blattebene-Funktion ist eine, die keine Funktionstabelleneintrag erforderlich ist. Es vornehmen keine Änderungen, um keine nicht flüchtigen Register, einschließlich der RSP, was bedeutet, dass keine Funktionen aufrufen oder Stack Speicherplatz belegt werden. Es ist zulässig, den Stapel nicht ausgerichtete zu verlassen, während es ausgeführt wird.

## <a name="malloc-alignment"></a>Malloc-Ausrichtung

["malloc"](../c-runtime-library/reference/malloc.md) ist immer, den Speicher zurück, die passend ausgerichtet ist, für das Speichern eines beliebigen Objekts, die eine grundlegende Ausrichtung und die hinsichtlich der Menge des Arbeitsspeichers unterbringen konnten, die zugeordnet wird. Ein *grundlegende Ausrichtung* ist eine Ausrichtung, die kleiner oder gleich der größten Ausrichtung, die von der Implementierung ohne Ausrichtungsspezifikation unterstützt wird. (In Visual C++ ist dies die Ausrichtung, die für einen `double` oder 8 Bytes erforderlich ist. In einem Code, der auf 64-Bit-Plattformen ausgerichtet ist, sind es 16 Bytes.) Beispielsweise kann eine Vier-Byte-Speicherbelegung an einer Begrenzung ausgerichtet werden, die ein Objekt unterstützt, das maximal vier Byte groß ist.

Visual C++ unterstützt Typen mit *über eine erweiterte Ausrichtung*, welche sind auch bekannt als *über-ausgerichtete* Typen. Beispielsweise die SSE-Typen [__m128](../cpp/m128.md) und `__m256`, sowie Typen, die mithilfe von deklariert werden `__declspec(align( n ))` , in denen `n` ist größer als 8, verfügen über eine erweiterte Ausrichtung. Eine Speicherausrichtung an einer Grenze, die für ein Objekt geeignet ist, das eine erweiterte Ausrichtung erfordert, wird von `malloc` nicht gewährleistet. Um Arbeitsspeicher für über-ausgerichtete Typen zuzuordnen, verwenden Sie [_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) und verwandte Funktionen.

## <a name="alloca"></a>alloca

[_alloca](../c-runtime-library/reference/alloca.md) ist erforderlich, um werden 16-Byte-ausgerichtet und Frame-Pointer verwenden.

Der Stapel, der zugeordnet wird Leerzeichen für Parameter, der anschließend aufgerufenen Funktionen, nachdem sie ein muss, wie unter [Stapelreservierung](#stack-allocation).

## <a name="see-also"></a>Siehe auch

[Softwarekonventionen bei x64-Systemen](../build/x64-software-conventions.md)<br/>
[align](../cpp/align-cpp.md)<br/>
[__declspec](../cpp/declspec.md)
