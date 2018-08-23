---
title: C++-Entwickler-Leitfaden für spekulative Ausführung dienstseitige Kanäle | Microsoft-Dokumentation
ms.custom: ''
ms.date: 07/10/2018
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Visual C++, security
- security [C++]
- security [C++], best practices
- Spectre
- CVE-2017-5753
- Speculative Execution
author: mamillmsft
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 378c6fe9a86cc44d80252f69367cf8c70234f469
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42613245"
---
# <a name="c-developer-guidance-for-speculative-execution-side-channels"></a>C++-Entwickler-Leitfaden für spekulative Ausführung dienstseitige Kanäle

Dieser Artikel enthält Anleitungen für Entwickler zur Unterstützung beim Identifizieren und Beheben von Sicherheitsrisiken durch spekulative Ausführung Seite Kanal Hardware in der C++-Software. Diese Sicherheitsrisiken können sensible Informationen offengelegt werden über Vertrauensgrenzen hinweg und können die Software, die auf Prozessoren ausgeführt wird, die spekulative Ausführung außerhalb der Reihenfolge von Anweisungen unterstützen beeinträchtigen. Diese Klasse von Sicherheitsrisiken wurde zuerst im Januar 2018 beschrieben und zusätzliche Hintergrundinformationen und Anleitungen finden Sie im [von Microsoft-sicherheitsempfehlung](https://portal.msrc.microsoft.com/security-guidance/advisory/ADV180002).

Die Anleitung in diesem Artikel bezieht sich auf die Klassen von Sicherheitsrisiken durch dargestellt:

1. CVE-2017-5753, auch bekannt als Spectre-Variante 1. Dieses Sicherheitsrisiko Hardwareklasse bezieht sich auf dienstseitige Kanäle, die aufgrund der spekulativen Ausführung auftreten können, die als Ergebnis eine bedingte Verzweigung Misprediction auftritt, haben. Visual C++-Compiler in Visual Studio 2017 (ab Version 15.5.5) bietet Unterstützung für die `/Qspectre` eine Lösung während der Kompilierung für eine begrenzte Anzahl von potenziell anfällige Codierungsmuster bietet-Schalter im Zusammenhang mit der CVE-2017-5753. Die Dokumentation für die ["/ qspectre"](https://docs.microsoft.com/cpp/build/reference/qspectre) Flag enthält weitere Informationen zu dessen Auswirkungen und Nutzung. 

2. CVE-2018-3639, auch bekannt als [spekulative Store umgehen (SSB)](https://aka.ms/sescsrdssb). Dieses Sicherheitsrisiko Hardwareklasse bezieht sich auf dienstseitige Kanäle, die aufgrund der spekulativen Ausführung eines Auslastungstests vor einem abhängigen Speicher als Ergebnis eine Arbeitsspeicher-Access-Misprediction auftreten können.

Einführung zugegriffen werden kann spekulative Ausführung Seite ausführungsseitigen channelsicherheitsanfälligkeiten finden Sie in der Präsentation, die mit dem Titel [die Groß-/Kleinschreibung der Spectre und Meltdown](https://www.youtube.com/watch?v=_4O0zMW-Zu4) von einem der Research-Teams, die diese Probleme ermittelt.

## <a name="what-are-speculative-execution-side-channel-hardware-vulnerabilities"></a>Was sind Spekulatives Ausführung Seite Kanal Hardware Sicherheitsrisiken?

Bei modernen CPUs höheres Maß an Leistung Geben Sie dazu mit der spekulativen und Out-of-Order-Ausführung von Anweisungen. Angenommen, dies erfolgt häufig Vorhersage des Ziels der Branches (bedingte und indirekte) dadurch die CPU als spekulativer Ausführung von Aufgaben im Ziel vorhergesagten Branch zu beginnen und so eine Verzögerungszeit, bis die tatsächlichen Verzweigungsziel ist aufgelöst. Wenn die CPU, dass eine Misprediction aufgetreten später ermittelt werden soll, werden alle Status des Computers, der spekulativer berechnet wurde verworfen. Dadurch wird sichergestellt, dass keine architektonisch sichtbaren Auswirkungen der mispredicted Spekulatives vorhanden sind.

Während der spekulativer Ausführung den architektonisch sichtbaren Zustand nicht beeinträchtigt, können sie residuale ablaufverfolgungen in nicht-Architektur Zustand befindet, z. B. die verschiedenen Caches lassen, die von der CPU verwendet werden. Es handelt sich um diese residual ablaufverfolgungen der spekulativen Ausführung, der zu Seite ausführungsseitigen channelsicherheitsanfälligkeiten führen können. Um dies zu verstehen, betrachten Sie das folgende Codefragment bietet ein Beispiel für CVE-2017-5753 (Begrenzungen überprüfen Umgehung) aus:

```cpp
// A pointer to a shared memory region of size 1MB (256 * 4096)
unsigned char *shared_buffer;

unsigned char ReadByte(unsigned char *buffer, unsigned int buffer_size, unsigned int untrusted_index) {
    if (untrusted_index < buffer_size) {
        unsigned char value = buffer[untrusted_index];
        return shared_buffer[value * 4096];
    }
}
```

In diesem Beispiel `ReadByte` ist ein Puffer, eine Puffergröße sowie einen Index in diesen Puffer angegeben. Der Indexparameter, laut `untrusted_index`, angegeben wird, mit einem kleiner privilegierten Kontext, z. B. ein Nichtadministrator-Prozess. Wenn `untrusted_index` ist kleiner als `buffer_size`, und klicken Sie dann das Zeichen an diesem Index aus der gelesen wird `buffer` und zum Index in ein freigegebener Speicherbereich verweist `shared_buffer`. 

Aus Sicht der Architektur, diese Codesequenz ist absolut sicher, da sichergestellt ist, die `untrusted_index` immer kleiner als `buffer_size`. Bei der spekulativen Ausführung, es ist jedoch möglich, dass die CPU wird die bedingten Verzweigung falschvorh, und führen Sie den Text zurück, wenn die Anweisung, auch wenn `untrusted_index` ist größer als oder gleich `buffer_size`. Daher kann die CPU einen Byte außerhalb der Grenzen des spekulativer lesen `buffer` (die möglicherweise einen geheimen Schlüssel) und klicken Sie dann, Byte-Wert verwenden können, um die Adresse einer nachfolgenden Last durch berechnen `shared_buffer`. 

Während die CPU dieses Misprediction schließlich erkannt werden, möglicherweise residual Nebeneffekte bleiben in der CPU-Cache, der Informationen zu den Bytewert anzuzeigen, die außerhalb des gültigen Bereichs von gelesen wurde `buffer`. Diese Nebenwirkungen kann erkannt werden, indem ein kleiner privilegierten Kontext, die auf dem System ausgeführt wird, wie schnell Überprüfung jeder Cache Zeile, in `shared_buffer` zugegriffen wird. Sind die Schritte, die ausgeführt werden können, um dies zu erreichen:

1. **Rufen Sie `ReadByte` mehrmals mit `untrusted_index` wird weniger als `buffer_size`** . Der angreifende Kontext kann dazu führen, dass das Opfer-Kontext aufrufen `ReadByte` (z. B. über RPC), der das Vorhersageergebnis Branch ist z. B. trainiert, um Sie als nicht durchgeführt werden `untrusted_index` ist kleiner als `buffer_size`.

2. **Alle Cachezeilen in leeren `shared_buffer`** . Der angreifende Kontext muss alle Cachezeilen, die in der Region freigegebenen Speicher verweist leeren `shared_buffer`. Da Arbeitsspeicherbereichs freigegeben wird, dies ist einfach und kann erreicht werden, mithilfe von systeminternen Funktionen wie z. B. `_mm_clflush`.

3. **Rufen Sie `ReadByte` mit `untrusted_index` größer als `buffer_size`** . Der angreifende Kontext bewirkt, dass das Opfer-Kontext aufrufen `ReadByte` so, dass es falsch vorhergesagt wird, dass die Verzweigung nicht ausgeführt werden. Dieser bewirkt, dass der Prozessor spekulativer führen Sie den Text der If-block mit `untrusted_index` größer als `buffer_size`, werden daher zu einer außerhalb des gültigen Bereichs lesen führende von `buffer`. Folglich `shared_buffer` werden indiziert, verwenden einen potenziell geheimen-Wert, der außerhalb des gültigen Bereichs, wodurch von der CPU geladen werden die jeweiligen Cachezeile gelesen wurde.

4. **Lesen jede Cachezeile in `shared_buffer` angezeigt, die am schnellsten zugegriffen wird**. Der angreifende Kontext erhalten jede Cachezeile in `shared_buffer` und erkennen die Cachezeile, die erheblich schneller als die anderen lädt. Dies ist die Cachezeile, die wahrscheinlich zu den Schritt 3 eingegeben wurden. Da eine 1:1-Beziehung zwischen Byte-Wert und die Cache-Zeile in diesem Beispiel ist, wird dadurch den Angreifer, den tatsächlichen Wert des Bytes abzuleiten, die außerhalb des gültigen Bereichs gelesen wurde.

Die oben genannten Schritte geben Sie ein Beispiel der Verwendung von Technik leeren + neu laden in Verbindung mit eine Instanz von CVE-2017-5753 ausnutzen.

## <a name="what-software-scenarios-can-be-impacted"></a>Welche Szenarien für die Software können betroffen sein?

Entwicklung von sicherer Software, die mit einem Prozess wie die [Security Development Lifecycle](https://www.microsoft.com/en-us/sdl/) (SDL) in der Regel muss die Vertrauensgrenzen zu identifizieren, die in der Anwendung vorhanden sind. An Orten, in denen eine Anwendung mit Daten von einem weniger vertrauenswürdigen Kontext, wie z. B. ein anderer Prozess auf dem System oder einen Benutzer ohne Administratorrechte-Modus-Prozess bei einem Kernelmodus-Gerätetreiber interagieren kann, ist eine Vertrauensgrenze vorhanden. Die neue Klasse von Sicherheitsrisiken, die im Zusammenhang mit spekulativer Ausführung dienstseitige Kanäle ist relevant für viele die Vertrauensgrenzen in Software Security Modelle, die Isolieren von Code und Daten auf einem Gerät. 

Die folgende Tabelle enthält eine Zusammenfassung der Software Sicherheitsmodelle, in denen Entwickler kümmern diese Sicherheitsrisiken, die auftreten müssen unter Umständen:

|Vertrauensgrenze|Beschreibung|
|----------------|----------------|
|Virtual Machine-Grenze|Anwendungen, die Isolierung von Workloads in separate virtuelle Computer, die nicht vertrauenswürdige Daten von einem anderen virtuellen Computer erhalten möglicherweise gefährdet.| 
|Kernelgrenze|Ein im Kernelmodus-Gerätetreiber, der nicht vertrauenswürdige Daten von einem Benutzer ohne Administratorrechte-Modus-Prozess empfängt möglicherweise gefährdet.| 
|Prozessgrenze|Eine Anwendung, die nicht vertrauenswürdige Daten von einem anderen Prozess ausgeführt wird, auf dem lokalen System, empfängt, wie z. B. über eine (Remoteprozeduraufruf), freigegebenen Speicher oder andere prozessübergreifende Kommunikation (IPC) Mechanismen gefährdet sein können.|
|Enclave-Grenze|Eine Anwendung, die in eine sichere Enclave (z. B. Intel SGX) ausgeführt wird, die nicht vertrauenswürdige Daten von außerhalb der Enclave empfängt möglicherweise gefährdet.|
|Sprachgrenze|Eine Anwendung, die interpretiert oder Just-in-Time (JIT) kompiliert und nicht vertrauenswürdigen Code in der führt eine höherrangige Sprache möglicherweise gefährdet.|

Anwendungen, die Angriffsfläche auf eine der oben genannten vertrauen, dass Code auf der Angriffsoberfläche zur Identifizierung und Minimierung von Instanzen der spekulativen Ausführung Seite ausführungsseitigen channelsicherheitsanfälligkeiten Grenzen geprüft werden soll. Anzumerken ist, dass die Vertrauensgrenzen verfügbar gemacht werden, um remote Angriffsflächen, z. B. remote Netzwerkprotokollen, nicht gezeigt wurde, um spekulative Ausführung Seite ausführungsseitigen channelsicherheitsanfälligkeiten gefährdet werden.

## <a name="potentially-vulnerable-coding-patterns"></a>Potenziell anfällige Codierungsmuster

Spekulative Ausführung Seite ausführungsseitigen channelsicherheitsanfälligkeiten können daher mehrere Codierungsmuster auftreten. In diesem Abschnitt wird beschrieben, potenziell anfällige Codierungsmuster und enthält Beispiele für die einzelnen allerdings, dass Variationen auf diese Themen vorhanden sind, können erkannt werden sollen. Entwickler werden daher empfohlen, diese Muster als Beispiele und nicht als eine vollständige Liste aller potenziell anfällige Codierungsmuster werden. Die gleichen Klassen Arbeitsspeicher Sicherheit Sicherheitsrisiken, die in der Software heute existieren kann auch zusammen mit spekulativer vorhanden sind, und Out-of-Order-Pfaden der Ausführung, aber nicht beschränkt auf Pufferüberläufe, einschließlich Arrays außerhalb des gültigen Bereichs zugreift, nicht initialisierter Speicher verwenden, geben Verwirrung und So weiter. Die gleichen Grundtypen, die Angreifer verwenden können, um Arbeitsspeicher Sicherheit Sicherheitslücken Architektur Pfaden ausnutzen können auch auf spekulative Pfade anwenden.

Im Allgemeinen kann spekulative Ausführung Seite Kanäle im Zusammenhang mit der bedingten Verzweigung Misprediction auftreten, wenn es sich bei ein bedingter Ausdruck für Daten ausgeführt wird, die gesteuert oder durch einen Kontext an weniger vertrauenswürdigen beeinflusst werden können. Dies kann z. B. einschließen bedingter Ausdrücke in `if`, `for`, `while`, `switch`, oder die ternäre Anweisungen. Für jede der folgenden Anweisungen generiert der Compiler kann einen bedingten Zweig, den die CPU klicken Sie dann das Branch-Ziel für die Laufzeit Vorhersagen kann.

Für jedes Beispiel wird ein Kommentar mit dem Begriff "SPEKULATIONSBARRIERE" eingefügt, in denen ein Entwickler eine Barriere als Risikominderung führen konnte. Dies wird ausführlicher im Abschnitt auf Schutzmaßnahmen erläutert.

## <a name="speculative-out-of-bounds-load"></a>Außerhalb des gültigen Bereichs Spekulatives Laden

Diese Kategorie von Codemuster umfasst eine bedingte Verzweigung Misprediction, die außerhalb des gültigen Bereichs für eine zu einer spekulativen führt Speicherzugriff.

### <a name="array-out-of-bounds-load-feeding-a-load"></a>Array außerhalb des gültigen Bereichs zu laden, fügen einem Auslastungstest

Dieses Codierungsmuster ist der ursprünglich beschrieben anfällig Codierungsmuster für CVE-2017-5753 (Begrenzungen überprüfen Umgehung). Die Hintergrund-Abschnitt dieses Artikels wird dieses Muster im Detail erläutert.

```cpp
// A pointer to a shared memory region of size 1MB (256 * 4096)
unsigned char *shared_buffer;

unsigned char ReadByte(unsigned char *buffer, unsigned int buffer_size, unsigned int untrusted_index) {
    if (untrusted_index < buffer_size) {
        // SPECULATION BARRIER
        unsigned char value = buffer[untrusted_index];
        return shared_buffer[value * 4096];
    }
}
```

Ein Array außerhalb des gültigen Bereichs Load in Verbindung mit einer Schleife auftreten kann, die die Beendigung überschreitet aufgrund einer Misprediction auf ähnliche Weise-Bedingung. In diesem Beispiel die bedingten Verzweigung zugeordnet der `x < buffer_size` Ausdruck falschvorh und führen Sie den Text der spekulativer kann die `for` Schleife beim `x` ist größer als oder gleich `buffer_size`, daher in einer spekulativen resultierende Laden Sie außerhalb des gültigen Bereichs.

```cpp
// A pointer to a shared memory region of size 1MB (256 * 4096)
unsigned char *shared_buffer;

unsigned char ReadBytes(unsigned char *buffer, unsigned int buffer_size) {
    for (unsigned int x = 0; x < buffer_size; x++) {
        // SPECULATION BARRIER
        unsigned char value = buffer[x];
        return shared_buffer[value * 4096];
    }
}
```

### <a name="array-out-of-bounds-load-feeding-an-indirect-branch"></a>Array außerhalb des gültigen Bereichs zu laden, fügen eine indirekte branch

Dieses Codierungsmuster umfasst den Fall, in denen eine bedingte Verzweigung Misprediction kann führen zu, einer außerhalb des gültigen Bereichs der Zugriff auf ein Array von Funktionszeigern, die dann führt zu einer indirekten Verzweigung an das Ziel zu, die beheben, außerhalb des gültigen Bereichs gelesen wurde. Der folgende Codeausschnitt enthält ein Beispiel, die dies veranschaulicht. 

In diesem Beispiel wird ein nicht vertrauenswürdiger Nachrichten-ID bereitgestellt, um DispatchMessage über die `untrusted_message_id` Parameter. Wenn `untrusted_message_id` ist kleiner als `MAX_MESSAGE_ID`, wird es in ein Array von Funktionszeigern, indizieren und branch verwendet das entsprechende Branch-Ziel. Dieser Code architektonisch sicher ist, aber wenn die CPU die bedingten Verzweigung falsch vorhergesagte zugeordnet werden, kann dies dazu führen `DispatchTable` von indizierten `untrusted_message_id` Wenn der Wert ist, größer als oder gleich `MAX_MESSAGE_ID`, werden daher führende zu einer außerhalb des gültigen Bereichs zuzugreifen. Dies kann spekulative Ausführung aus der einer Zieladresse Branch führen, die über die Grenzen des Arrays abgeleitet ist, was zur Offenlegung von Informationen je nach Code führen konnte, die spekulativer ausgeführt wird.

```cpp
#define MAX_MESSAGE_ID 16

typedef void (*MESSAGE_ROUTINE)(unsigned char *buffer, unsigned int buffer_size);

const MESSAGE_ROUTINE DispatchTable[MAX_MESSAGE_ID];

void DispatchMessage(unsigned int untrusted_message_id, unsigned char *buffer, unsigned int buffer_size) {
    if (untrusted_message_id < MAX_MESSAGE_ID) {
        // SPECULATION BARRIER
        DispatchTable[untrusted_message_id](buffer, buffer_size);
    }
}
```

Wie im Fall eines Arrays außerhalb des gültigen Bereichs laden, fügen einen anderen laden, kann diese Bedingung auch in Verbindung mit einer Schleife auftreten, die der abschließende Zustand aufgrund einer Misprediction überschreitet.

### <a name="array-out-of-bounds-store-feeding-an-indirect-branch"></a>Außerhalb des gültigen Bereichs Array speichern, fügen eine indirekte branch

Während das vorherige Beispiel wie eine spekulative außerhalb des gültigen Bereichs beeinflussen die Auslastung kann eine indirekte Verzweigungsziel zeigte, es ist auch möglich, dass ein außerhalb des gültigen Bereichs speichern, um eine indirekte Branch-Ziel, z. B. einen Funktionszeiger oder eine Absenderadresse zu ändern. Dies kann potenziell zur spekulative Ausführung von einem Angreifer Adresse führen.

In diesem Beispiel wird ein nicht vertrauenswürdiger Index durch Übergeben der `untrusted_index` Parameter. Wenn `untrusted_index` ist kleiner als die Anzahl der Elemente von der `pointers` Array (256 Elemente), und klicken Sie dann auf den Wert des bereitgestellten Zeigers, in `ptr` bezieht sich auf die `pointers` Array. Dieser Code architektonisch sicher ist, aber wenn die CPU die bedingten Verzweigung falsch vorhergesagte zugeordnet werden, kann dies dazu führen `ptr` spekulativer geschrieben wird, über die Grenzen des dem Stapel zugeordneten `pointers` Array. Dies kann zu einer Beschädigung der spekulativen der Absenderadresse für führen `WriteSlot`. Wenn ein Angreifer, den Wert der steuern kann `ptr`, sie möglicherweise dazu führen, dass bei der spekulativen Ausführung über einen beliebigen behandeln, wenn `WriteSlot` entlang des Pfads spekulative zurückgibt.

```cpp
unsigned char WriteSlot(unsigned int untrusted_index, void *ptr) {
    void *pointers[256];
    if (untrusted_index < 256) {
        // SPECULATION BARRIER
        pointers[untrusted_index] = ptr;
    }
}
```

Auf ähnliche Weise, wenn eine lokale Variable Zeiger Funktion mit dem Namen `func` möglich, ändern Sie die Adresse spekulativer möglicherweise auf dem Stapel zugeordnet wurden, `func` bedeutet, dass die bedingte Verzweigung Misprediction tritt auf. Dies könnte, wenn der Funktionszeiger, durch aufgerufen wird spekulative Ausführung von einer beliebigen Adresse führen.

```cpp
unsigned char WriteSlot(unsigned int untrusted_index, void *ptr) {
    void *pointers[256];
    void (*func)() = &callback;
    if (untrusted_index < 256) {
        // SPECULATION BARRIER
        pointers[untrusted_index] = ptr;
    }
    func();
}
```

Anzumerken ist, dass in beiden Beispielen spekulative Änderung der Stapel zugeordneten indirekte branchzeiger umfassen. Es ist möglich, dass die spekulative Änderung auch für globale Variablen, den Heap reservierte Speicher und sogar schreibgeschützten Speicher für einige CPUs auftreten kann. Für den Stapel zugeordneten Arbeitsspeicher wird Visual C++-Compiler noch Maßnahmen erschweren spekulativer indirekte Branch Stapel zugeordneten Ziele, z. B. durch die neuanordnung von lokalen Variablen, sodass Puffer ein Sicherheitscookie als nebeneinander platziert werden geändert Teil der [/GS](https://docs.microsoft.com/cpp/build/reference/gs-buffer-security-check) Compiler Sicherheitsfunktion.

## <a name="speculative-type-confusion"></a>Spekulative Typ Verwirrung

Diese Kategorie behandelt Codemuster, die zu einer spekulativen Typ zu Verwirrung führen können. Dies tritt auf, wenn Speicher mit einem falschen Typ auf einem nicht-Architektur Pfad während der spekulativen Ausführung zugegriffen wird. Sowohl der bedingte Verzweigung Misprediction als auch der spekulativen Store umgehen können potenziell ein spekulative Typ Verwirrung stiften. 

Zur Umgehung der spekulativen Store kann dies in Szenarien auftreten, in denen ein Compiler eine Stapelspeicherort für Variablen mehrerer Typen verwendet. Grund hierfür ist der architektonische Speicher für eine Variable vom Typ `A` möglicherweise umgangen werden, sodass die Last des Typs `A` spekulativer ausgeführt werden, bevor der Variablen zugewiesen wird. Wenn die zuvor gespeicherte Variable eines anderen Typs ist, können Sie dies die Bedingungen für eine Verwechslung spekulative Typ erstellen.

Für bedingte Verzweigung Misprediction, die im folgenden Codeausschnitt verwendet werden, um zu beschreiben verschiedene Bedingungen, die spekulative Typ Verwirrung bereitstellen kann steigt.

```cpp
enum TypeName {
    Type1,
    Type2
};

class CBaseType {
public:
    CBaseType(TypeName type) : type(type) {}
    TypeName type;
};

class CType1 : public CBaseType {
public:
    CType1() : CBaseType(Type1) {}
    char field1[256];
    unsigned char field2;
};

class CType2 : public CBaseType {
public:
    CType2() : CBaseType(Type2) {}
    void (*dispatch_routine)();
    unsigned char field2;
};

// A pointer to a shared memory region of size 1MB (256 * 4096)
unsigned char *shared_buffer;

unsigned char ProcessType(CBaseType *obj)
{
    if (obj->type == Type1) {
        // SPECULATION BARRIER
        CType1 *obj1 = static_cast<CType1 *>(obj);

        unsigned char value = obj1->field2;

        return shared_buffer[value * 4096];
    }
    else if (obj->type == Type2) {
        // SPECULATION BARRIER
        CType2 *obj2 = static_cast<CType2 *>(obj);

        obj2->dispatch_routine();

        return obj2->field2;
    }
}
```

### <a name="speculative-type-confusion-leading-to-an-out-of-bounds-load"></a>Spekulative Typ zu Verwirrung führt zu einer außerhalb des gültigen Bereichs geladen werden.

Dieses Codierungsmuster umfasst den Fall, in denen eine Verwechslung spekulative Typ dazu führen kann, ein außerhalb des gültigen Bereichs oder Feldzugriff, in dem der geladene Wert eine Adresse für nachfolgende Feeds, Typ verwechselt. Dieser Vorgang das Schreiben von Code außerhalb des gültigen Bereichs Arraymuster ähnelt, aber es über eine Alternative, die Codierung der Sequenz wie oben gezeigt angezeigt wird. In diesem Beispiel den Kontext ein angreifenden kann dazu führen, dass Opfer Kontext zum Ausführen `ProcessType` mehrmals mit einem Objekt vom Typ `CType1` (`type` Feld ist gleich `Type1`). Dies hat den Effekt des Trainings für des bedingten Branch für die erste `if` -Anweisung nicht die Vorhersagen. Angreifende Kontext kann bewirken, dass den Opfer Kontext zum Ausführen `ProcessType` mit einem Objekt vom Typ `CType2`. Dies kann in einer Verwirrung spekulative Typ führen, wenn der bedingte Ausdruck für die erste Verzweigung `if` Anweisung falsch vorhergesagte zugeordnet, und führt den Hauptteil des der `if` -Anweisung, daher Umwandlung eines Objekts vom Typ `CType2` zu `CType1`. Da `CType2` ist kleiner als `CType1`, die Arbeitsspeicher-Zugriff auf `CType1::field2` führen zu einer spekulativen außerhalb des gültigen Bereichs lädt Daten, die geheim sein kann. Dieser Wert wird dann verwendet, bei einem Auslastungstest aus `shared_buffer` können die wahrnehmbaren Nebeneffekte, wie mit dem Array erstellen außerhalb des gültigen Bereichs Beispiel oben beschriebenen.

### <a name="speculative-type-confusion-leading-to-an-indirect-branch"></a>Spekulative Typ zu Verwirrung führt zu einer indirekten Verzweigung

Dieses Codierungsmuster umfasst den Fall, in denen eine Verwechslung spekulative Typ einer unsicheren indirekte Verzweigung während der spekulativen Ausführung führen kann. In diesem Beispiel den Kontext ein angreifenden kann dazu führen, dass Opfer Kontext zum Ausführen `ProcessType` mehrmals mit einem Objekt vom Typ `CType2` (`type` Feld ist gleich `Type2`). Dies hat den Effekt des Trainings für des bedingten Branch für die erste `if` Anweisung an, die ausgeführt werden und die `else if` -Anweisung nicht ausgeführt werden. Angreifende Kontext kann bewirken, dass den Opfer Kontext zum Ausführen `ProcessType` mit einem Objekt vom Typ `CType1`. Dies kann in einer Verwirrung spekulative Typ führen, wenn der bedingte Ausdruck für die erste Verzweigung `if` Anweisung vorhersagt ausgeführt und die `else if` den Text der Anweisung nicht ausgeführt wird, vorhersagt somit Ausführen der `else if` und ein Objekt des Typs umwandeln`CType1` zu `CType2`. Da die `CType2::dispatch_routine` Feld überschneidet sich mit den `char` Array `CType1::field1`, könnte dies in einer spekulativen indirekte Verzweigung, um eine unbeabsichtigte Verzweigungsziel. Wenn der angreifende Kontext der Bytewerte in steuern kann die `CType1::field1` Array ist, sie können möglicherweise die Zieladresse für den Branch zu steuern.

## <a name="speculative-uninitialized-use"></a>Spekulative nicht initialisierten verwenden

Diese Kategorie von Codemuster umfasst Szenarien, in denen spekulativer Ausführung möglicherweise nicht initialisierten Speicher zugreifen und verwenden Sie es in nachfolgenden auslastungs- oder indirekte Branch. Für diese Codierungsmuster für die ausgenutzt werden muss ein Angreifer in der Lage, um zu steuern oder beeinflussen sinnvoll, den Inhalt des Arbeitsspeichers, der verwendet wird, ohne Initialisierung durch den Kontext an, dem sie in verwendet wird.

### <a name="speculative-uninitialized-use-leading-to-an-out-of-bounds-load"></a>Spekulative nicht initialisierten verwenden, was zu einer außerhalb des gültigen Bereichs geladen

Spekulative nicht initialisierte Verwendung kann führt möglicherweise zu einer außerhalb des gültigen Bereichs zu laden, indem ein Angreifer gesteuerte-Wert. Im folgenden Beispiel wird der Wert des `index` erhält `trusted_index` in allen Architektur Pfaden und `trusted_index` wird als kleiner als oder gleich `buffer_size`. Je nach den Code, der vom Compiler erzeugten, es ist jedoch möglich, dass eine Umgehung spekulative Speicher auftreten kann, die die Last für ermöglicht `buffer[index]` und abhängigen Ausdrücken zum Ausführen vor der Zuweisung zu `index`. In diesem Fall einen nicht initialisierten Wert für `index` verwendet werden, als der Offset in `buffer` der Angreifer könnten vertrauliche Informationen außerhalb des gültigen Bereichs, und übermittelt dies über einen Kanal Seite über die abhängige Last `shared_buffer` .

```cpp
// A pointer to a shared memory region of size 1MB (256 * 4096)
unsigned char *shared_buffer;

void InitializeIndex(unsigned int trusted_index, unsigned int *index) {
    *index = trusted_index;
}

unsigned char ReadByte(unsigned char *buffer, unsigned int buffer_size, unsigned int trusted_index) {
    unsigned int index;

    InitializeIndex(trusted_index, &index); // not inlined

    // SPECULATION BARRIER
    unsigned char value = buffer[index];
    return shared_buffer[value * 4096];
}
```

### <a name="speculative-uninitialized-use-leading-to-an-indirect-branch"></a>Spekulative nicht initialisierten verwenden, was zu einer indirekten Verzweigung

Eine spekulative nicht initialisierte Verwendung kann potenziell zur eine indirekte Branch führen, in denen das Verzweigungsziel ist von einem Angreifer gesteuert. Im folgenden Beispiel wird `routine` wird zugewiesen, entweder `DefaultMessageRoutine1` oder `DefaultMessageRoutine` abhängig vom Wert `mode`. Auf dem Architektur-Pfad, führt dies zu `routine` immer vor dem indirekten Branch initialisiert wird. Je nach den Code, der vom Compiler erzeugten, eine Umgehung spekulative Store kann jedoch auftreten, die über die indirekte Verzweigung ermöglicht `routine` spekulativer vor der Zuweisung zu auszuführende `routine`. In diesem Fall ein Angreifer möglicherweise spekulativer führen Sie über eine beliebige Adresse, sofern der Angreifer beeinflussen kann, oder kontrollieren den nicht initialisierten Wert `routine`.

```cpp
#define MAX_MESSAGE_ID 16

typedef void (*MESSAGE_ROUTINE)(unsigned char *buffer, unsigned int buffer_size);

const MESSAGE_ROUTINE DispatchTable[MAX_MESSAGE_ID];
extern unsigned int mode;

void InitializeRoutine(MESSAGE_ROUTINE *routine) {
    if (mode == 1) {
        *routine = &DefaultMessageRoutine1;
    }
    else {
        *routine = &DefaultMessageRoutine;
    }
}

void DispatchMessage(unsigned int untrusted_message_id, unsigned char *buffer, unsigned int buffer_size) {
    MESSAGE_ROUTINE routine;

    InitializeRoutine(&routine); // not inlined

    // SPECULATION BARRIER
    routine(buffer, buffer_size);
}
```

## <a name="mitigation-options"></a>Migrationsoptionen

Spekulative Ausführung Seite ausführungsseitigen channelsicherheitsanfälligkeiten können durch Änderungen an den Quellcode verringert werden. Diese Änderungen können umfassen Beheben von bestimmten Instanzen einer Sicherheitsanfälligkeit, z. B. durch Hinzufügen einer *spekulationsbarriere*, oder durch Änderungen am Entwurf einer Anwendung sensiblen Informationen für spekulative Sperren die Ausführung.

### <a name="speculation-barrier-via-manual-instrumentation"></a>Spekulationsbarriere über manuelle Instrumentierung

Ein *spekulationsbarriere* manuell von einem Entwickler, um zu verhindern, dass bei der spekulativen Ausführung fortgesetzt, die entlang eines Pfads ohne architektonische eingefügt werden kann. Beispielsweise kann ein Entwickler eine spekulationsbarriere vor einem riskantes Codierungsmuster einfügen, im Hauptteil einen bedingten Block ein, entweder am Anfang des Blocks (nachdem Sie den bedingten Branch) oder vor dem ersten Laden, die relevant ist. Dadurch wird verhindert, dass eine bedingte Verzweigung Misprediction aus den gefährlichen Code serialisieren Sie die Ausführung auf einem nicht-Architektur Pfad ausführen. Spekulatives Barriere Sequenz unterscheidet sich von der Hardware-Architektur, wie in der folgenden Tabelle beschrieben:

|Architektur|Systeminterne für CVE-2017-5753 spekulationsbarriere|Systeminterne für CVE-2018-3639 spekulationsbarriere|
|----------------|----------------|----------------|
|X86/x64|_mm_lfence()|_mm_lfence()|
|ARM|aktuell nicht verfügbar|__dsb(0)|
|ARM64|aktuell nicht verfügbar|__dsb(0)|

Z. B. den folgenden Code, Muster kann behoben werden, mithilfe der `_mm_lfence` systeminterne wie unten dargestellt.

```cpp
// A pointer to a shared memory region of size 1MB (256 * 4096)
unsigned char *shared_buffer;

unsigned char ReadByte(unsigned char *buffer, unsigned int buffer_size, unsigned int untrusted_index) {
    if (untrusted_index < buffer_size) {
        _mm_lfence();
        unsigned char value = buffer[untrusted_index];
        return shared_buffer[value * 4096];
    }
}
```

### <a name="speculation-barrier-via-compiler-time-instrumentation"></a>Spekulationsbarriere über Compiler-Time-instrumentation

Visual C++-Compiler in Visual Studio 2017 (ab Version 15.5.5) bietet Unterstützung für die `/Qspectre` fügt automatisch eine spekulationsbarriere für einen begrenzten Satz von potenziell anfällige Codierungsmuster-Schalter im Zusammenhang mit der CVE-2017-5753. Die Dokumentation für die ["/ qspectre"](https://docs.microsoft.com/en-us/cpp/build/reference/qspectre) Flag enthält weitere Informationen zu dessen Auswirkungen und Nutzung. Es ist wichtig zu beachten, dass dieses Flag nicht alle der potenziell anfällige Codierungsmuster deckt und als solche Entwickler nicht darauf als eine umfassende Lösung für diese Klasse von Sicherheitsrisiken basieren sollten.

### <a name="masking-array-indices"></a>Maskieren von Arrayindizes

In Fällen, in denen außerhalb des gültigen Bereichs ein Spekulatives Laden, kann auftreten, der Arrayindex stark auf die Architektur und nicht-Architektur Pfad umschlossen werden kann durch Hinzufügen der Logik, um den Index des Arrays explizit gebunden. Z. B. wenn ein Array auf eine Größe zugewiesen werden kann, die in eine Potenz von zwei ausgerichtet ist, können Sie dann eine einfache Maske eingeführt werden. Dies wird veranschaulicht, in das folgende Beispiel, in denen es davon, dass ausgegangen wird `buffer_size` eine Potenz von zwei ausgerichtet ist. Dadurch wird sichergestellt, dass `untrusted_index` ist immer kleiner als `buffer_size`, auch wenn eine bedingte Verzweigung Misprediction tritt ein, und `untrusted_index` übergebene mit einem Wert größer als oder gleich `buffer_size`.

Es sollte darauf hingewiesen werden, dass die Index-Maske, die hier ausgeführt unterliegt spekulative Store umgehen, je nach Code könnte, die vom Compiler generiert wird.

```cpp
// A pointer to a shared memory region of size 1MB (256 * 4096)
unsigned char *shared_buffer;

unsigned char ReadByte(unsigned char *buffer, unsigned int buffer_size, unsigned int untrusted_index) {
    if (untrusted_index < buffer_size) {
        untrusted_index &= (buffer_size - 1);
        unsigned char value = buffer[untrusted_index];
        return shared_buffer[value * 4096];
    }
}
```

### <a name="removing-sensitive-information-from-memory"></a>Vertraulichen Informationen entfernt aus dem Arbeitsspeicher.

Ein weiteres Verfahren, das zum Verringern von Sicherheitsrisiken in spekulativer Ausführung Seite Channel verwendet werden kann ist, vertrauliche Informationen aus dem Arbeitsspeicher zu entfernen. Software-Entwickler können Suchen Sie nach Möglichkeiten, ihre Anwendung Umgestalten, dass der Zugriff auf vertraulicher Informationen während der spekulativen Ausführung nicht zugänglich ist. Dies kann durch den Entwurf einer Anwendung zum Isolieren von vertraulichen Informationen in separaten Prozessen refactoring erfolgen. Beispielsweise kann eine Web-Browser-Anwendung versuchen, um die Daten, die jeder Web-Ursprung in separate Prozesse, daher verhindert, dass ein Prozess kann für Cross-Origin-Datenzugriff durch spekulative Ausführung zugeordnet zu isolieren.

## <a name="see-also"></a>Siehe auch

[Anleitungen zum Verringern von Sicherheitsrisiken in seitenkanalangriffe mit spekulativer Ausführung](https://portal.msrc.microsoft.com/security-guidance/advisory/ADV180002)

[Beheben von Sicherheitsrisiken durch spekulative Ausführung Seite Kanal hardware](https://blogs.technet.microsoft.com/srd/2018/03/15/mitigating-speculative-execution-side-channel-hardware-vulnerabilities/)