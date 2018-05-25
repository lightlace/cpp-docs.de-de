---
title: C++-Entwickler-Leitfaden für spekulative Ausführung dienstseitige Kanäle | Microsoft Docs
ms.custom: ''
ms.date: 05/21/2018
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
ms.author: mikeblome
ms.workload:
- cplusplus
ms.openlocfilehash: 515e2223e67d86da12488d9880a1a0a258fc4bdf
ms.sourcegitcommit: 4b2c3b0c720aef42bce7e1e5566723b0fec5ec7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2018
---
# <a name="c-developer-guidance-for-speculative-execution-side-channels"></a>C++-Entwickler-Leitfaden für spekulative Ausführung dienstseitige Kanäle

Dieser Artikel enthält Hinweise für Entwickler, die Ihnen dabei helfen zu identifizieren und Beheben von spekulative Ausführung clientseitigen Kanal Hardware Sicherheitsrisiken in der C++-Software. Diese Sicherheitslücken über Vertrauensgrenzen hinweg können vertraulichen Informationen offen legen und können Software, die auf Prozessoren ausgeführt wird, die spekulative Ausführung außerhalb der Reihenfolge von Anweisungen unterstützen beeinträchtigen. Diese Klasse von Sicherheitsrisiken wurde zuerst im Januar, 2018 beschrieben und zusätzliche Hintergrundinformationen und Hinweise finden Sie im [des Microsoft Security advisory](https://portal.msrc.microsoft.com/en-US/security-guidance/advisory/ADV180002).

Die Anleitungen in diesem Artikel bezieht sich auf die Klassen von Sicherheitsrisiken durch dargestellt:

1. CVE-2017-5753, auch bekannt als Absorptionsspektrum Variante 1. Dieses Sicherheitsrisiko Hardwareklasse bezieht sich auf dienstseitige Kanäle, die aufgrund von spekulative Ausführung auftreten können, die als Ergebnis eine bedingte Verzweigung Misprediction auftritt. Der Visual C++-Compiler in Visual Studio 2017 (ab Version 15.5.5) bietet Unterstützung für die `/Qspectre` -Schalter, die eine Verringerung der Zeitpunkt der Kompilierung für eine begrenzte Anzahl von potenziell gefährdet Codierungsmuster stellt im Zusammenhang mit CVE-2017-5753. Die Dokumentation für die [/Qspectre](https://docs.microsoft.com/en-us/cpp/build/reference/qspectre) Flag enthält ausführlichere Informationen zu seiner Auswirkungen und Nutzung.

2. CVE-2018-3639, auch bekannt als [spekulative Store umgehen (SSB)](https://aka.ms/sescsrdssb). Dieses Sicherheitsrisiko Hardwareklasse bezieht sich auf dienstseitige Kanäle, die aufgrund der Ausführung eines Auslastungstests vor einem abhängigen Speicher als Ergebnis einer Arbeitsspeicher Zugriff Misprediction spekulative entstehen können.

Einführung in zugegriffen werden kann die spekulative Ausführung clientseitigen Kanal Sicherheitsrisiken finden Sie in der Präsentation mit dem Titel [die Groß-/Kleinschreibung Absorptionsspektrum und überdauern](https://www.youtube.com/watch?v=_4O0zMW-Zu4) eines Research-Teams, die diese Probleme ermittelt.

## <a name="what-are-speculative-execution-side-channel-hardware-vulnerabilities"></a>Was sind Spekulatives Ausführung clientseitigen Kanal Hardware Sicherheitsrisiken?

Moderne CPUs bieten höheren Grad an Leistung stammschlüsselpaars spekulative und außerhalb der Reihenfolge die Ausführung der Anweisungen verwenden. Beispielsweise wird oft dies durch das Ziel der Verzweigungen (bedingte und indirekte) Dadurch kann die CPU als beginnen spekulativ Ausführung von Anweisungen auf das vorhergesagte Verzweigungsziel Vorhersagen daher eine Zurückhalten zu vermeiden, bis das tatsächliche Verzweigungsziel ist aufgelöst. Wenn die CPU-Nutzung später stellt fest, dass ein Misprediction aufgetreten ist, werden alle Status des Computers, der spekulativ berechnet wurde verworfen. Dadurch wird sichergestellt, dass keine architektonisch sichtbaren Auswirkungen mispredicted Spekulatives vorhanden sind.

Während der Ausführung spekulative den architektonischen sichtbaren Zustand beeinträchtigt wird, können sie residuale ablaufverfolgungen in nicht-Architektur Status, wie die verschiedenen Caches lassen, die durch die CPU verwendet werden. Es ist diese residualen Spuren des spekulative ausgeführt werden, die clientseitigen Kanal Sicherheitsrisiken hervorrufen können. Betrachten Sie das folgende Codefragment, das bietet ein Beispiel für CVE 2017 5753 (Grenzen überprüfen umgehen), zum besseren Verständnis:

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

In diesem Beispiel `ReadByte` ist ein Puffer, die Puffergröße und ein Index in diesen Puffer angegeben. Der Indexparameter entsprechend den Angaben von `untrusted_index`, angegeben wird, mit einem kleiner privilegierten Kontext, z. B. ein Nichtadministrator-Prozess. Wenn `untrusted_index` ist kleiner als `buffer_size`, und klicken Sie dann das Zeichen an diesem Index gelesen `buffer` und verwendeten Index in einen freigegebenen Bereich des Arbeitsspeichers verweist auf `shared_buffer`. 

Aus Sicht der Architektur dieses Codesequenz ist vollkommen sicher, da sichergestellt ist, `untrusted_index` immer kleiner als `buffer_size`. Wiederherstellungsprobleme spekulative Ausführung, es ist jedoch möglich, dass die CPU wird bedingte Verzweigung mispredict und führen Sie den Text zurück, wenn die Anweisung auch dann, wenn `untrusted_index` ist größer als oder gleich `buffer_size`. Daher die CPU möglicherweise spekulativ liest ein Byte außerhalb der Grenzen des `buffer` (die möglicherweise einen geheimen Schlüssel) und konnte den Bytewert dann verwenden, um die Adresse einer nachfolgenden Last durch berechnen `shared_buffer`. 

Während die CPU dieses Misprediction schließlich erkennt, residual Nebeneffekte möglicherweise bleiben in der CPU-Cache, der Informationen zu den Bytewert offenlegen, die außerhalb des gültigen Bereichs von gelesen wurde `buffer`. Diese Nebeneffekte können erkannt werden, ein kleiner privilegierten Kontext, die auf dem System ausgeführt wird, wie schnell Überprüfung jeder Cache in Zeile `shared_buffer` zugegriffen wird. Sind die Schritte, die ausgeführt werden können, um dies zu erreichen:

1. **Aufrufen `ReadByte` mehrmals mit `untrusted_index` wird weniger als `buffer_size`** . Nun Kontext kann dazu führen, dass das Opfer Kontext aufzurufenden `ReadByte` (z. B. über RPC), der das Vorhersageergebnis Verzweigung ist z. B. als nicht durchgeführt werden trainiert `untrusted_index` ist kleiner als `buffer_size`.

2. **Alle Cachezeilen in leeren `shared_buffer`** . Nun Kontext muss alle Cachezeilen in der freigegebene Bereich des Arbeitsspeichers verweist auf leeren `shared_buffer`. Da der Speicherbereich gemeinsam verwendet wird, dies ist einfach und kann mithilfe von systeminternen Funktionen wie z. B. umgesetzt werden `_mm_clflush`.

3. **Aufrufen `ReadByte` mit `untrusted_index` größer als `buffer_size`** . Nun Kontext bewirkt, dass das Opfer Kontext aufzurufenden `ReadByte` , dass sie falsch vorhergesagt, dass die Verzweigung nicht ausgeführt wird. Dadurch wird der Prozessor spekulativ führen Sie den Text der If-block mit `untrusted_index` größer als `buffer_size`, daher was zu einer schreibgeschützten außerhalb des Bereichs der `buffer`. Folglich `shared_buffer` indiziert mit einem potenziell für den geheimen-Wert, der außerhalb des Bereichs, wodurch die jeweiligen Cachezeile von der CPU geladen werden gelesen wurde.

4. **Lesen jede Cachezeile in `shared_buffer` angezeigt, die am schnellsten zugegriffen wird**. Nun Kontext kann in jeder Cachezeile lesen `shared_buffer` erkannt werden, die Cachezeile, die erheblich schneller als das andere lädt. Dies ist die Cachezeile, die wahrscheinlich Schritt 3 eingegeben wurden. Da eine 1:1-Beziehung zwischen Byte-Wert und der Cache-Zeile in diesem Beispiel besteht, kann der Angreifer den tatsächlichen Wert des Bytes ableiten, die außerhalb des Bereichs gelesen wurde.

Die oben genannten Schritte geben Sie ein Beispiel über eine bekannte als leeren + neu laden in Verbindung mit eine Instanz von CVE-2017-5753 ausnutzen Technik.

## <a name="what-software-scenarios-can-be-impacted"></a>Welche Szenarien Software beeinträchtigt werden können?

Entwickeln von sicheren Software, die mit einem Prozess wie die [Security Development Lifecycle](https://www.microsoft.com/en-us/sdl/) (SDL) in der Regel müssen Sie die Vertrauensgrenzen hinweg zu identifizieren, die in ihrer Anwendung vorhanden sein. Eine Vertrauensgrenze vorhanden ist, in der Orte, wo eine Anwendung mit Daten von einem weniger vertrauenswürdigen Kontext, z. B. einem anderen Prozess auf dem System oder einen Benutzer ohne Administratorrechte Modus Prozess im Falle eines Gerätetreibers im Kernelmodus interagieren kann. Die neue Klasse von Sicherheitsrisiken im Zusammenhang mit spekulative Ausführung dienstseitige Kanäle ist relevant für viele der Vertrauensgrenzen hinweg in vorhandenen Sicherheitsmodelle für Software, die Code und Daten auf einem Gerät zu isolieren. 

Die folgende Tabelle enthält einen Überblick über die Software Sicherheitsmodelle, in dem betreffenden Informationen zu diesen Sicherheitsrisiken auftreten werden Entwickler müssen möglicherweise:

|Vertrauensstellungsgrenze|Beschreibung|
|----------------|----------------|
|Begrenzung des virtuellen Computers|Anwendungen, die arbeitsauslastungen auf jeweils eigenen virtuellen Computern zu isolieren, die nicht vertrauenswürdige Daten von einem anderen virtuellen Computer empfangen möglicherweise gefährdet sein.| 
|Kernelgrenze|Ein Kernel-Modus-Gerätetreiber, der nicht vertrauenswürdige Daten von einem Benutzer ohne Administratorrechte Modus Prozess empfängt möglicherweise gefährdet.| 
|Prozessgrenze|Eine Anwendung, die nicht vertrauenswürdige Daten aus einem anderen Prozess auf dem lokalen System ausgeführten empfängt, z. B. über einen Remoteprozeduraufruf (RPC), freigegebenen Speicher oder andere prozessübergreifende Kommunikation (IPC) Mechanismen gefährdet sein könnte.|
|Enclave Grenze|Eine Anwendung, die innerhalb einer sicheren Enclave (z. B. Intel SGX) ausgeführt wird, die nicht vertrauenswürdige Daten von außerhalb der Enclave empfängt möglicherweise gefährdet.|
|Language-Grenze|Eine Anwendung, die interpretiert oder Just-in-Time (JIT) kompiliert und führt nicht vertrauenswürdigen Code geschrieben wird, eine höherrangige Sprache möglicherweise gefährdet sein.|

Anwendungen, die Angriffsfläche verfügbar gemacht zu den oben vertrauen, dass Grenzen Code auf die Angriffsfläche zu identifizieren und Beheben von möglichen Instanzen spekulative Ausführung clientseitigen Kanal Sicherheitsrisiken überprüfen sollten. Beachten Sie, dass Vertrauensgrenzen verfügbar gemacht werden, um remote Angriffsflächen, z. B. remote Netzwerkprotokollen, nicht gefährdet, spekulative Ausführung clientseitigen Kanal Sicherheitsrisiken nachgewiesen wurde.

## <a name="potentially-vulnerable-coding-patterns"></a>Potenziell gefährdet Codierungsmuster

Als Folge mehrere Codierungsmuster können spekulative Ausführung clientseitigen Kanal Sicherheitslücken entstehen. In diesem Abschnitt wird beschrieben, potenziell gefährdet Codierungsmuster und enthält Beispiele für die einzelnen jedoch Variationen bei diesen Designs vorhanden sind, können erkannt werden sollen. Daher sollten Entwickler diese Muster als Beispiele und nicht als eine vollständige Liste aller potenziell gefährdet Codierungsmuster akzeptieren.

Im Allgemeinen kann spekulative Ausführung clientseitigen Kanäle für die bedingte Verzweigung Misprediction entstehen, wenn ein bedingter Ausdruck für Daten ausgeführt wird, die kontrolliert oder von einem weniger vertrauenswürdigen Kontext beeinflusst werden können. Dies kann z. B. bedingte Ausdrücke in enthalten `if`, `for`, `while`, `switch`, oder ternäre-Anweisungen. Für jede dieser Anweisungen generiert der Compiler kann eine bedingte Verzweigung, die die CPU klicken Sie dann das Verzweigungsziel für zur Laufzeit Vorhersagen kann.

Für jedes Beispiel, in dem ein Entwickler eine Barriere als linderungsmaßnahme einführen konnte ein Kommentar mit dem Begriff "SPEKULATIVES BARRIERE" eingefügt. Dies wird ausführlicher im Abschnitt für linderungsmaßnahmen erläutert.

## <a name="speculative-out-of-bounds-load"></a>Außerhalb des Bereichs Spekulatives Laden

Diese Kategorie von Codierungsmuster umfasst eine bedingte Verzweigung Misprediction, die außerhalb des Bereichs zu einem spekulative führt Speicherzugriff.

### <a name="array-out-of-bounds-load-feeding-a-load"></a>Laden von Arrays außerhalb des Bereichs gespeist eines Auslastungstests

Dieses Codierungsmuster ist ursprünglich beschrieben anfällig Codierungsmuster für CVE 2017 5753 (Grenzen überprüfen umgehen). Im Hintergrund Abschnitt dieses Artikels wird dieses Muster im Detail erläutert.

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

Ein Array außerhalb des Bereichs Load in Verbindung mit einer Schleife auftreten kann, die ihre beendet überschreitet aufgrund einer Misprediction auf ähnliche Weise-Bedingung. In diesem Beispiel zugeordneten bedingte Verzweigung der `x < buffer_size` Ausdruck mispredict und führen Sie den Text der spekulativ möglicherweise die `for` Schleife, wenn `x` ist größer als oder gleich `buffer_size`daher ergibt eine spekulative außerhalb des Bereichs geladen Sie werden.

```cpp
// A pointer to a shared memory region of size 1MB (256 * 4096)
unsigned char *shared_buffer;

unsigned char ReadBytes(unsigned char *buffer, unsigned int buffer_size) {
    for (unsigned int x = 0; x < buffer_size; x++) {
        // SPECULATION BARRIER
        unsigned char value = buffer[untrusted_index];
        return shared_buffer[value * 4096];
    }
}
```

### <a name="array-out-of-bounds-load-feeding-an-indirect-branch"></a>Laden von Arrays außerhalb des Bereichs gespeist einer indirekten Verzweigung

Dieses Codierungsmuster umfasst die Groß-/Kleinschreibung, in denen eine bedingte Verzweigung Misprediction zu führen kann, ein außerhalb des Bereichs der Zugriff auf ein Array von Funktionszeigern, welche dann führt zu einer indirekten Verzweigung an das Ziel zu, die befassen, außerhalb des Bereichs gelesen wurde. Der folgende Codeausschnitt veranschaulicht, die dies veranschaulicht. 

In diesem Beispiel wird ein nicht vertrauenswürdiger Nachrichten-ID bereitgestellt, um DispatchMessage über die `untrusted_message_id` Parameter. Wenn `untrusted_message_id` ist kleiner als `MAX_MESSAGE_ID`, wird dieser index in ein Array von Funktionszeigern und zum Verzweigen verwendet die entsprechenden Verzweigungsziel. Dieser Code architektonisch sicher ist, aber wenn die CPU die bedingte Verzweigung mispredicts, kann dies dazu führen `DispatchTable` von indizierten `untrusted_message_id` Wenn der Wert ist größer als oder gleich `MAX_MESSAGE_ID`, daher was zu einer außerhalb des gültigen Bereichs zuzugreifen. Dies kann zu spekulative Ausführung über die Zieladresse einer Verzweigung führen, die außerhalb des zulässigen Bereichs des Arrays abgeleitet werden, was zur Offenlegung von Informationen je nach den Code führen konnte, die spekulativ ausgeführt wird.

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

Wie für den Fall eines Arrays außerhalb des Bereichs laden eine andere Last generiert, kann diese Bedingung auch in Verbindung mit einer Schleife auftreten, die die abschließende Zustand aufgrund einer Misprediction überschreitet.

## <a name="speculative-type-confusion"></a>Spekulatives Typ Verwirrung

Diese Kategorie behandelt die Codierung Muster, die eine Verwechslung spekulative Typ hervorrufen können. Dies tritt auf, wenn Speicher mit inkorrekten Typs entlang eines Pfads ohne architektonische während der Ausführung spekulative zugegriffen wird. Bedingte Verzweigung Misprediction und spekulative Store umgehen können zu einer spekulativen Typ zu Verwirrung führen. 

Für spekulative Store umgehen kann dies in Szenarien auftreten, in denen ein Compiler eine Stapelspeicherort für Variablen mehrere Arten wiederverwendet. Grund hierfür ist der Architektur Speicher für eine Variable vom Typ `A` möglicherweise umgangen werden, wodurch die Last des Typs `A` spekulativ ausgeführt werden, bevor der Variablen zugewiesen ist. Wenn die zuvor gespeicherte Variable eines anderen Typs ist, kann dies die Bedingungen für eine Verwechslung spekulative Typ erstellen.

Für bedingte Verzweigung Misprediction, die im folgenden Codeausschnitt verwendet werden, um zu beschreiben verschiedene Bedingungen, mit denen spekulative Typ Verwirrung erhalten kann steigen.

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

### <a name="speculative-type-confusion-leading-to-an-out-of-bounds-load"></a>Spekulatives Typ Verwirrung zu einer außerhalb des Bereichs zu laden

Dieses Codierungsmuster umfasst die Groß-/Kleinschreibung, in denen eine Verwechslung spekulative Typs dazu führen kann, ein außerhalb des Bereichs oder Typ verwechselt Feldzugriff, in denen der geladene Wert eine Adresse nachfolgende des feeds. Dies ist vergleichbar mit dem Array außerhalb des Bereichs Codierungsmuster, aber es wird über eine Alternative Codierung Sequenz, wie oben gezeigt auswirken. In diesem Beispiel könnte ein nun Kontext Opfer Kontext zum Ausführen `ProcessType` mehrere Male mit einem Objekt des Typs `CType1` (`type` Feld ist gleich `Type1`). Dies hat den Effekt des Trainings für der bedingten Verzweigung für die erste `if` Anweisung nicht getroffenen Vorhersagen. Nun Kontext kann bewirken, dass das Opfer Kontext zum Ausführen `ProcessType` mit einem Objekt vom Typ `CType2`. Dadurch kann eine Verwechslung spekulative Typ, wenn der bedingte Ausdruck für die erste Verzweigung `if` Anweisung mispredicts und führt die `if` -Anweisung, also ein Objekt vom Typ umwandeln `CType2` auf `CType1`. Da `CType2` ist kleiner als `CType1`, den Speicherzugriff zu `CType1::field2` wird in einer spekulativen außerhalb des Bereichs Laden von Daten, die möglicherweise für den geheimen. Dieser Wert wird dann verwendet, in einer Last von `shared_buffer` können die Observable Nebeneffekte, wie mit dem Array erstellt außerhalb des Bereichs Beispiel zuvor beschriebenen.

### <a name="speculative-type-confusion-leading-to-an-indirect-branch"></a>Spekulatives Typ Verwirrung führt zu einer indirekten Verzweigung

Dieses Codierungsmuster umfasst die Groß-/Kleinschreibung, in denen eine Verwechslung spekulative Typ in einem unsicheren indirekte Branch während der Ausführung spekulative führen kann. In diesem Beispiel könnte ein nun Kontext Opfer Kontext zum Ausführen `ProcessType` mehrere Male mit einem Objekt des Typs `CType2` (`type` Feld ist gleich `Type2`). Dies hat den Effekt des Trainings für der bedingten Verzweigung für die erste `if` Anweisung an, die ausgeführt werden und die `else if` Anweisung an, die nicht ausgeführt werden. Nun Kontext kann bewirken, dass das Opfer Kontext zum Ausführen `ProcessType` mit einem Objekt vom Typ `CType1`. Dadurch kann eine Verwechslung spekulative Typ, wenn der bedingte Ausdruck für die erste Verzweigung `if` Anweisung vorhersagt ausgeführt und die `else if` den Text der Anweisung vorhersagt, nicht ausgeführt, somit Ausführen der `else if` und Umwandlung eines Objekts vom Typ `CType1` auf `CType2`. Da die `CType2::dispatch_routine` Feld überschneidet sich mit den `char` Array `CType1::field1`, könnte dies in einer spekulativen indirekte Verzweigung, um eine unbeabsichtigte Verzweigungsziel. Wenn nun Kontext, die Bytewerte in steuern kann der `CType1::field1` Array, möglicherweise die Zieladresse der Verzweigung zu steuern.

## <a name="speculative-uninitialized-use"></a>Spekulatives nicht initialisierten verwenden

Diese Kategorie von Codierungsmuster umfasst Szenarien, in dem spekulative Ausführung nicht initialisierten Speicher zugreifen kann, und verwenden, um einen nachfolgenden Laden oder eine indirekte Verzweigung feed. Für diese Codierungsmuster ausgenutzt werden muss ein Angreifer möglicherweise steuern oder beeinflussen sinnvoll, den Inhalt des Arbeitsspeichers, der verwendet wird, nicht initialisierte vom Kontext, dem sie in verwendet wird.

### <a name="speculative-uninitialized-use-leading-to-an-out-of-bounds-load"></a>Spekulatives nicht initialisierten verwenden, die zu einer außerhalb des Bereichs zu laden

Eine spekulative nicht initialisierte Verwendung kann potenziell dazu führen, dass eine mit einem Angreifer gesteuert Wert außerhalb des Bereichs zu laden. Im folgenden Beispiel ist der Wert der `index` zugewiesen `trusted_index` auf alle architektonische Pfade und `trusted_index` wird davon ausgegangen, dass kleiner als oder gleich `buffer_size`. Je nach den Code, der vom Compiler erzeugten, es ist jedoch möglich, dass eine Umgehung spekulative Speicher auftreten kann, die die Last von ermöglicht `buffer[index]` und abhängigen Ausdrücke auszuführende vor der Zuweisung zur `index`. In diesem Fall für einen nicht initialisierten Wert `index` verwendet werden, wie der Offset `buffer` ermöglichen die Angreifer außerhalb des Bereichs vertraulichen Informationen lesen, und übermittelt diese über einen Kanal Seite über der abhängigen Laden von `shared_buffer` .

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

### <a name="speculative-uninitialized-use-leading-to-an-indirect-branch"></a>Spekulatives nicht initialisierten verwenden, die zu einer indirekten Verzweigung

Eine nicht initialisierte spekulative Verwendung kann zu einer indirekten Verzweigung führen, in denen das Verzweigungsziel wird von einem Angreifer gesteuert. Im folgenden Beispiel wird `routine` wird zugewiesen, entweder `DefaultMessageRoutine1` oder `DefaultMessageRoutine` abhängig vom Wert des `mode`. Auf dem architektonische Pfad, führt dies zu `routine` immer vor der indirekten Verzweigung initialisiert wird. Je nach den vom Compiler generierten Code eine Umgehung spekulative Store kann jedoch auftreten, die über die indirekte Verzweigung ermöglicht `routine` spekulativ vor der Zuweisung zur auszuführenden `routine`. In diesem Fall ein Angreifer möglicherweise von einer beliebigen Adresse spekulativ ausführen vorausgesetzt der Angreifer beeinflussen kann, oder kontrollieren den nicht initialisierten Wert `routine`.

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

## <a name="mitigation-options"></a>Entschärfung-Optionen

Spekulatives Ausführung clientseitigen Kanal Sicherheitsrisiken können durch Änderungen an der Quellcode verringert werden. Diese Änderungen können zwar Abhilfe für bestimmte Instanzen von ein Sicherheitsrisiko dar, z. B. durch Hinzufügen einer *Spekulatives Barriere*, oder durch Änderungen am Entwurf von einer Anwendung, die vertraulichen Informationen sorgen, dass spekulative können die Ausführung.

### <a name="speculation-barrier-via-manual-instrumentation"></a>Spekulatives Barriere über manuelle instrumentation

Ein *Spekulatives Barriere* manuell von einem Entwickler spekulative Ausführung nicht fortgesetzt entlang eines Pfads ohne architektonische verhindern eingefügt werden. Beispielsweise kann ein Entwickler ein Hindernis Spekulatives, bevor Sie einen gefährlichen Codierungsmuster einfügen, im Text eines bedingten Blocks, entweder am Anfang des Blocks (nach den bedingten Branch) oder vor dem ersten Laden, die relevant ist. Hierdurch wird eine bedingte Verzweigung Misprediction aus den gefährlichen Code durch serialisieren Sie die Ausführung auf einem nicht-Architektur Pfad ausführen. Spekulatives Barriere Sequenz unterscheidet sich vom Hardware-Architektur, wie in der folgenden Tabelle beschrieben:

|Architektur|Spekulatives Barriere systeminterne für CVE-2017-5753|Spekulatives Barriere systeminterne für CVE-2018-3639|
|----------------|----------------|----------------|
|X86/x64|_mm_lfence()|_mm_lfence()|
|ARM|Derzeit nicht verfügbar|__dsb(0)|
|ARM64|Derzeit nicht verfügbar|__dsb(0)|

Beispielsweise kann der folgende Code, Muster verringert werden, durch die Verwendung der `_mm_lfence` systeminterne wie unten dargestellt.

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

### <a name="speculation-barrier-via-compiler-time-instrumentation"></a>Spekulatives Barriere über Compiler-Time-instrumentation

Der Visual C++-Compiler in Visual Studio 2017 (ab Version 15.5.5) bietet Unterstützung für die `/Qspectre` -Schalter, mit eine Barriere Spekulatives für eine begrenzte Anzahl von potenziell gefährdet Codierungsmuster automatisch fügt im Zusammenhang mit CVE-2017-5753. Die Dokumentation für die [/Qspectre](https://docs.microsoft.com/en-us/cpp/build/reference/qspectre) Flag enthält ausführlichere Informationen zu seiner Auswirkungen und Nutzung. Es ist wichtig zu beachten, dass dieses Flag nicht alle potenziell gefährdet Codierungsmuster deckt und als solche Entwickler sollten Sie sich nicht darauf als eine umfassende Lösung für diese Klasse von Sicherheitsrisiken.

## <a name="masking-array-indices"></a>Arrayindizes maskieren

In Fällen, in denen außerhalb des Bereichs einer Spekulatives Laden, auftreten, der Arrayindex stark auf die Architektur und nicht architektonische Pfad umschlossen werden kann durch Hinzufügen von Logik, um den Index des Arrays explizit gebunden. Z. B. wenn ein Array eine Größe zugewiesen werden kann, die in eine Potenz von zwei ausgerichtet ist, können Sie dann eine einfache Maske eingeführt werden. Dies wird im Beispiel unten, wo es davon, dass ausgegangen wird, veranschaulicht `buffer_size` in eine Potenz von zwei ausgerichtet ist. Dadurch wird sichergestellt, dass `untrusted_index` ist immer kleiner als `buffer_size`, selbst wenn eine bedingte Verzweigung Misprediction tritt auf, und `untrusted_index` übergebene mit einem Wert größer als oder gleich `buffer_size`.

Beachten Sie, dass die Index Maskierung hier durchgeführten unterliegt spekulative Store umgehen abhängig vom Code konnte, die vom Compiler generiert wird.

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

## <a name="removing-sensitive-information-from-memory"></a>Vertraulichen Informationen entfernt aus dem Arbeitsspeicher.

Eine andere Technik, die verwendet werden kann, um spekulative Ausführung clientseitigen Kanal Sicherheitsrisiken zu minimieren ist, die vertrauliche Informationen aus dem Arbeitsspeicher zu entfernen. Softwareentwickler können Suchen Sie nach Möglichkeit, ihre Anwendung Umgestalten, dass der Zugriff auf vertraulicher Informationen während der Ausführung spekulative nicht möglich ist. Dies kann durch den Entwurf einer Anwendung mit vertraulichen Informationen in separate Prozesse isolieren Umgestaltung erfolgen. Beispielsweise kann eine Webbrowseranwendung versuchen, zugeordneten jeder Web Ursprung in getrennten Prozessen, daher verhindert, dass ein Prozess wird Cross-Origin-Daten über spekulative Ausführung Zugriff auf Daten zu isolieren.

## <a name="see-also"></a>Siehe auch

[Hinweise zum spekulative Ausführung Seiten-Kanal Sicherheitsrisiken zu minimieren](https://portal.msrc.microsoft.com/en-US/security-guidance/advisory/ADV180002)
[Abhilfe spekulative Ausführung clientseitigen Kanal Hardware Sicherheitsrisiken](https://blogs.technet.microsoft.com/srd/2018/03/15/mitigating-speculative-execution-side-channel-hardware-vulnerabilities/)