---
title: ARM64-Ausnahmebehandlung
description: Beschreibt die Ausnahme Behandlungs Konventionen und-Daten, die von Windows auf ARM64 verwendet werden.
ms.date: 11/19/2018
ms.openlocfilehash: 1ed147a27cfeb545e2a5fe265df8113a5befac73
ms.sourcegitcommit: 170f5de63b0fec8e38c252b6afdc08343f4243a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/11/2019
ms.locfileid: "72276833"
---
# <a name="arm64-exception-handling"></a>ARM64-Ausnahmebehandlung

Windows on ARM64 verwendet den gleichen Mechanismus für die strukturierte Ausnahmebehandlung für asynchrone, von der Hardware generierte Ausnahmen und synchrone Software generierte Ausnahmen. Sprachspezifische Ausnahmehandler werden auf von Windows strukturierter Ausnahmebehandlung mithilfe von Sprachhilfsfunktionen erstellt. In diesem Dokument wird die Ausnahmebehandlung in Windows auf ARM64 und die sprach Hilfsprogramme beschrieben, die von Code verwendet werden, der vom Microsoft-Arm-Assembler und dem MSVC-Compiler generiert wird.

## <a name="goals-and-motivation"></a>Ziele und Motivation

Die Ausnahme bei der Entwickelung von Daten Konventionen und diese Beschreibung sind folgende:

1. Stellen Sie eine ausreichende Beschreibung bereit, um das entwickeln ohne Code Tests in allen Fällen zuzulassen.

   - Um den Code zu analysieren, muss der Code in das Pager eingefügt werden. Dies verhindert, dass es in einigen Fällen sinnvoll ist (Ablauf Verfolgung, Sampling, Debuggen).

   - Das Analysieren des Codes ist komplex. der Compiler muss darauf achten, nur Anweisungen zu generieren, die der Entlader decodieren kann.

   - Wenn das Entladen nicht durch die Verwendung von Entladungs Codes vollständig beschrieben werden kann, muss es in einigen Fällen auf die Anweisungs Decodierung zurückgreifen. Dies erhöht die Gesamtkomplexität und wird idealerweise vermieden.

1. Unterstützung der Entwickelung in Mid-Prolog und Mid-Epilog.

   - Die Entwickelung wird in Windows für mehr als Ausnahmebehandlung verwendet. Es ist wichtig, dass der Code auch dann korrekt entladen werden kann, wenn er sich in der Mitte einer Prolog-oder epilogcodefolge befindet.

1. Nehmen Sie eine minimale Menge an Speicherplatz in Anspruch.

   - Die Entladungs Codes dürfen nicht aggregiert werden, um die binäre Größe erheblich zu erhöhen.

   - Da die Entladungs Codes wahrscheinlich im Speicher gesperrt sind, stellt ein kleiner Speicherbedarf einen minimalen mehr Aufwand für jede geladene Binärdatei sicher.

## <a name="assumptions"></a>Annahmen

Diese Annahmen werden in der Ausnahme Behandlungs Beschreibung vorgenommen:

1. Prologs und Epilogs spiegeln tendenziell beides wider. Durch die Nutzung dieses allgemeinen Merkmals kann die Größe der Metadaten, die zum Beschreiben der Entwickelung erforderlich sind, erheblich reduziert werden. Im Hauptteil der Funktion ist es unerheblich, ob die Vorgänge des Prologs rückgängig gemacht werden, oder die Vorgänge des epiprotokolls werden vorwärts ausgeführt. Beides sollte zum gleichen Ergebnis führen.

1. Die Funktionen sind tendenziell relativ klein. Mehrere Optimierungen für den Speicherplatz basieren auf dieser Tatsache, um das effizienteste Verpacken von Daten zu erreichen.

1. Es gibt keinen bedingten Code in Epilogs.

1. Dediziertes Frame Zeiger Register: Wenn der SP in einem anderen Register (x29) im Prolog gespeichert wird, bleibt dieses Register in der gesamten Funktion unverändert. Dies bedeutet, dass der ursprüngliche SP jederzeit wieder hergestellt werden kann.

1. Wenn der SP nicht in einem anderen Register gespeichert wird, erfolgt die gesamte Bearbeitung des Stapel Zeigers nur im Prolog und Epilog.

1. Das Stapel Rahmen Layout ist so organisiert, wie im nächsten Abschnitt beschrieben.

## <a name="arm64-stack-frame-layout"></a>ARM64 Stapel Rahmen Layout

Stapel Rahmen(media/arm64-exception-handling-stack-frame.png "Layout") für ![Stapel Rahmen Layout]

Bei Frame verketteten Funktionen können das FP-und LR-Paar in Abhängigkeit von Optimierungs Überlegungen an jeder beliebigen Position im lokalen Variablen Bereich gespeichert werden. Das Ziel besteht darin, die Anzahl der lokalen Variablen zu maximieren, die durch eine einzelne Anweisung erreicht werden können, die auf dem Frame Zeiger (x29) oder dem Stapelzeiger (SP) basiert. Für `alloca`-Funktionen muss Sie jedoch verkettet werden, und x29 muss auf den unteren Rand des Stapels zeigen. Um eine bessere Abdeckung im Register-paar-Adressierungs Modus zu ermöglichen, werden nicht flüchtige Registrierungs Speicherbereiche am oberen Rand des lokalen Stapel Bereichs positioniert. Im folgenden finden Sie Beispiele, die einige der effizientesten Prolog Sequenzen veranschaulichen. Um Klarheit und eine bessere Cache Lokalität zu erzielen, wird die Reihenfolge der Speicherung gespeicherter Register in allen kanonischen Prologe in der Reihenfolge "wächst" angezeigt. `#framesz` unten steht für die Größe des gesamten Stapels (mit Ausnahme des Bereichs "Zuweisung"). `#localsz` und `#outsz` kennzeichnen die Größe des lokalen Bereichs (einschließlich des Speicherbereichs für das \<x29, LR > Paar) bzw. die ausgehende Parameter Größe.

1. Verkettet, #localsz \< = 512

    ```asm
        stp    x19,x20,[sp,#-96]!        // pre-indexed, save in 1st FP/INT pair
        stp    d8,d9,[sp,#16]            // save in FP regs (optional)
        stp    x0,x1,[sp,#32]            // home params (optional)
        stp    x2,x3,[sp,#48]
        stp    x4,x5,[sp,#64]
        stp    x6,x7,[sp,#72]
        stp    x29,lr,[sp,#-localsz]!   // save <x29,lr> at bottom of local area
        mov    x29,sp                   // x29 points to bottom of local
        sub    sp,sp,#outsz             // (optional for #outsz != 0)
    ```

1. Verkettet, #localsz > 512

    ```asm
        stp    x19,x20,[sp,#-96]!        // pre-indexed, save in 1st FP/INT pair
        stp    d8,d9,[sp,#16]            // save in FP regs (optional)
        stp    x0,x1,[sp,#32]            // home params (optional)
        stp    x2,x3,[sp,#48]
        stp    x4,x5,[sp,#64]
        stp    x6,x7,[sp,#72]
        sub    sp,sp,#(localsz+outsz)   // allocate remaining frame
        stp    x29,lr,[sp,#outsz]       // save <x29,lr> at bottom of local area
        add    x29,sp,#outsz            // setup x29 points to bottom of local area
    ```

1. Nicht verkettete Blatt Funktionen (LR nicht gespeichert)

    ```asm
        stp    x19,x20,[sp,#-80]!       // pre-indexed, save in 1st FP/INT reg-pair
        stp    x21,x22,[sp,#16]
        str    x23,[sp,#32]
        stp    d8,d9,[sp,#40]           // save FP regs (optional)
        stp    d10,d11,[sp,#56]
        sub    sp,sp,#(framesz-80)      // allocate the remaining local area
    ```

   Der Zugriff auf alle lokalen Variablen erfolgt basierend auf SP. \<x29, LR > auf den vorherigen Frame zeigt. Für Frame Size \< = 512, "Sub SP,..." kann optimiert werden, wenn der gespeicherte regs-Bereich an den unteren Rand des Stapels verschoben wird. Der Nachteil ist, dass er nicht mit anderen Layouts übereinstimmt, und gespeicherte Umleitungen nehmen einen Teil des Bereichs für paar Umleitungen und den vorab-und Post indizierten Offset-Adressierungs Modus.

1. Nicht verkettete, nicht Blatt Funktionen (LR wird im Bereich "int-gespeichert" gespeichert)

    ```asm
        stp    x19,x20,[sp,#-80]!       // pre-indexed, save in 1st FP/INT reg-pair
        stp    x21,x22,[sp,#16]         // ...
        stp    x23,lr,[sp,#32]          // save last Int reg and lr
        stp    d8,d9,[sp,#48]           // save FP reg-pair (optional)
        stp    d10,d11,[sp,#64]         // ...
        sub    sp,sp,#(framesz-80)      // allocate the remaining local area
    ```

   Oder bei einer geraden Anzahl gespeicherter int-Register

    ```asm
        stp    x19,x20,[sp,#-80]!       // pre-indexed, save in 1st FP/INT reg-pair
        stp    x21,x22,[sp,#16]         // ...
        str    lr,[sp,#32]              // save lr
        stp    d8,d9,[sp,#40]           // save FP reg-pair (optional)
        stp    d10,d11,[sp,#56]         // ...
        sub    sp,sp,#(framesz-80)      // allocate the remaining local area
    ```

   Nur x19 gespeichert:

    ```asm
        sub    sp,sp,#16                // reg save area allocation*
        stp    x19,lr,[sp]              // save x19, lr
        sub    sp,sp,#(framesz-16)      // allocate the remaining local area
    ```

   \*: die Zuordnung des reg-Speicherbereichs wird nicht in die STP-Datenbank gefaltet, weil eine vorindizierte reg-LR-STP nicht mit den Entladungs Codes dargestellt werden kann.

   Der Zugriff auf alle lokalen Variablen erfolgt basierend auf SP. \<x29 > verweist auf den vorherigen Frame.

1. Verkettet, #framesz \< = 512, #outsz = 0

    ```asm
        stp    x29,lr,[sp,#-framesz]!       // pre-indexed, save <x29,lr>
        mov    x29,sp                       // x29 points to bottom of stack
        stp    x19,x20,[sp,#(framesz-32)]   // save INT pair
        stp    d8,d9,[sp,#(framesz-16)]     // save FP pair
    ```

   Im Vergleich zum ersten obigen Prolog-Beispiel besteht der Vorteil darin, dass alle Register-Speicher Anweisungen für die Ausführung nach nur einer Stapel Zuordnungs Anweisung zur Ausführung bereit sind. Dies bedeutet, dass keine Abhängigkeit von SP vorliegt, die eine Parallelität auf Anweisungs Ebene verhindert.

1. Verkettete Frame Größe > 512 (optional für Funktionen ohne Zuweisung)

    ```asm
        stp    x29,lr,[sp,#-80]!            // pre-indexed, save <x29,lr>
        stp    x19,x20,[sp,#16]             // save in INT regs
        stp    x21,x22,[sp,#32]             // ...
        stp    d8,d9,[sp,#48]               // save in FP regs
        stp    d10,d11,[sp,#64]
        mov    x29,sp                       // x29 points to top of local area
        sub    sp,sp,#(framesz-80)          // allocate the remaining local area
    ```

   Für Optimierungszwecke kann x29 an jeder beliebigen Position im lokalen Bereich abgelegt werden, um eine bessere Abdeckung für den "reg-Pair"-und den Pre-/Post-Indexed Offset-Adressierungs Modus bereitzustellen. Auf lokale Variablen unterhalb von Frame Zeigern kann basierend auf SP zugegriffen werden.

1. Verkettet, Rahmengröße > 4K mit oder ohne Zuweisung (),

    ```asm
        stp    x29,lr,[sp,#-80]!            // pre-indexed, save <x29,lr>
        stp    x19,x20,[sp,#16]             // save in INT regs
        stp    x21,x22,[sp,#32]             // ...
        stp    d8,d9,[sp,#48]               // save in FP regs
        stp    d10,d11,[sp,#64]
        mov    x29,sp                       // x29 points to top of local area
        mov    x15,#(framesz/16)
        bl     __chkstk
        sub    sp,sp,x15,lsl#4              // allocate remaining frame
                                            // end of prolog
        ...
        sub    sp,sp,#alloca                // more alloca() in body
        ...
                                            // beginning of epilog
        mov    sp,x29                       // sp points to top of local area
        ldp    d10,d11,[sp,#64]
        ...
        ldp    x29,lr,[sp],#80              // post-indexed, reload <x29,lr>
    ```

## <a name="arm64-exception-handling-information"></a>ARM64-Ausnahme Behandlungsinformationen

### <a name="pdata-records"></a>. pdata-Datensätze

Bei den pData-Datensätzen handelt es sich um ein geordnetes Array von Elementen fester Länge, die jede Stapel Manipulations Funktion in einer PE-Binärdatei beschreiben. Der Ausdruck "Stapel Bearbeitung" ist von Bedeutung: Blatt Funktionen, die keinen lokalen Speicher erfordern und keine nicht flüchtigen Register speichern/wiederherstellen müssen, benötigen keinen pData-Datensatz. Diese Datensätze sollten explizit weggelassen werden, um Speicherplatz zu sparen. Eine Entladung von einer dieser Funktionen kann die Rückgabeadresse direkt von LR erhalten, um zum Aufrufer zu wechseln.

Jeder pData-Datensatz für ARM64 hat eine Länge von 8 Bytes. Im allgemeinen Format jedes Datensatzes wird die 32-Bit-RVA der Funktion im ersten Wort gestartet, gefolgt von einem zweiten Wort, das entweder einen Zeiger auf einen. XData-Block mit variabler Länge enthält, oder ein gepacktes Wort, das eine Sequenz für die Entwickelung einer kanonischen Funktion beschreibt.

![pData]-Daten Satz Layout(media/arm64-exception-handling-pdata-record.png ". pdata-Daten Satz Layout")

Die Felder lauten wie folgt:

- **RVA für Funktions Start** ist die 32-Bit-RVA des Starts der Funktion.

- **Flag** ist ein 2-Bit-Feld, das angibt, wie die verbleibenden 30 Bits des zweiten. pdata-Worts interpretiert werden. Wenn **Flag** gleich 0 ist, bilden die übrigen Bits eine **RVA der Ausnahme Informationen** (mit den zwei niedrigsten Bits implizit 0). Wenn das **Flag** ungleich 0 (null) ist, bilden die übrigen Bits eine **gepackte Entladedaten** Struktur.

- **Ausnahme Informationen RVA** ist die Adresse der Struktur der Ausnahme Informationen mit variabler Länge, die im Abschnitt. XData gespeichert ist. Diese Daten müssen 4-Bytes ausgerichtet sein.

- **Gepackte Entladedaten** sind eine komprimierte Beschreibung der Vorgänge, die zum Entladen von einer Funktion erforderlich sind, vorausgesetzt, eine kanonische Form. In diesem Fall ist kein .xdata-Datensatz erforderlich.

### <a name="xdata-records"></a>. XData-Datensätze

Wenn das gepackte Entladeformat nicht zur Beschreibung der Entladung einer Funktion ausreicht, muss ein .xdata-Datensatz mit variabler Länge erstellt werden. Die Adresse dieses Datensatzes wird im zweiten Wort des .pdata-Datensatzes gespeichert. Das Format von XData ist ein gepackter Satz von Wörtern mit variabler Länge:

![. XData]-Daten Satz Layout(media/arm64-exception-handling-xdata-record.png ". XData-Daten Satz Layout")

Diese Daten sind in vier Abschnitte unterteilt:

1. Ein 1-oder 2-Wort-Header, der die Gesamtgröße der Struktur und die Bereitstellung von Schlüssel Funktionsdaten beschreibt. Das zweite Wort ist nur vorhanden, wenn die Felder **epilogcount** und **Code Words** auf 0 festgelegt sind. Der Header weist diese Bitfelder auf:

   a. Die **Funktions Länge** ist ein 18-Bit-Feld. Gibt die Gesamtlänge der Funktion in Bytes geteilt durch 4 an. Wenn eine Funktion größer als 1 m ist, müssen mehrere. pdata-und. XData-Datensätze verwendet werden, um die Funktion zu beschreiben. Weitere Informationen finden Sie im Abschnitt zu [großen Funktionen](#large-functions) .

   b. **Vers** ist ein 2-Bit-Feld. Es beschreibt die Version der restlichen. XData. Derzeit ist nur Version 0 definiert, sodass die Werte von 1-3 nicht zulässig sind.

   c. **X** ist ein 1-Bit-Feld. Gibt das vorhanden sein (1) oder das Fehlen (0) von Ausnahme Daten an.

   d. **E** ist ein 1-Bit-Feld. Er gibt an, dass Informationen, die ein einzelnes Epilogcode beschreiben, in den Header (1) verpackt werden, anstatt zusätzliche Bereichs Wörter später (0) zu erfordern.

   e. Die **epilogcount** ist ein 5-Bit-Feld, das je nach Status des **E** -Bit zwei Bedeutungen hat:

      1. Wenn **E** 0 ist, wird die Anzahl der in Abschnitt 2 beschriebenen epilogbereiche angegeben. Wenn in der Funktion mehr als 31 Bereiche vorhanden sind, muss das Feld " **Code Wörter** " auf 0 festgelegt werden, um anzugeben, dass ein Erweiterungs Wort erforderlich ist.

      2. Wenn **E** 1 ist, gibt dieses Feld den Index des ersten Entladungs Codes an, der das einzige Epilog beschreibt.

   f. **Code Wörter** sind ein 5-Bit-Feld, das die Anzahl der 32-Bit-Wörter angibt, die erforderlich sind, um alle Entladungs Codes in Abschnitt 3 zu enthalten. Wenn mehr als 31 Wörter erforderlich sind (d. h., wenn mehr als 124 Entladungs Code Bytes vorhanden sind), muss dieses Feld den Wert 0 aufweisen, um anzugeben, dass ein Erweiterungs Wort erforderlich ist.

   g. **Erweiterte epilogcount** -und **Erweiterte Code Wörter** sind jeweils 16-Bit-und 8-Bit-Felder. Sie stellen mehr Speicherplatz für die Codierung einer ungewöhnlich großen Anzahl von Epilogs oder eine ungewöhnlich große Anzahl von Entladungs Codewörtern bereit. Das Erweiterungs Wort, das diese Felder enthält, ist nur vorhanden, wenn die Felder " **Epilog count** " und " **Code Words** " im ersten Header Wort den Wert "0" haben.

1. Wenn **epilogcount** nicht 0 ist, wird eine Liste mit Informationen zu epilogbereichen, die in ein Wort gepackt sind, nach dem Header und dem optionalen erweiterten Header gesendet. Sie werden in der Reihenfolge gespeichert, in der Sie den Start Offset erhöhen Jeder Bereich enthält die folgenden Bits:

   a. Der **Epilogcode-Start Offset** ist ein 18-Bit-Feld, das den Offset in Bytes (dividiert durch 4) des Epilogcode relativ zum Anfang der Funktion aufweist.

   b. **Res** ist ein 4-Bit-Feld, das für zukünftige Erweiterungen reserviert ist. Sein Wert muss 0 sein.

   c. Der **Epilog-Start Index** ist ein 10-Bit-Feld (2 mehr Bits als **Erweiterte Code Wörter**). Gibt den Byte Index des ersten Entladungs Codes an, der dieses Epilog beschreibt.

1. Die Liste der epilogbereiche enthält ein Bytearray, das Entladungs Codes enthält, die in einem späteren Abschnitt ausführlich beschrieben werden. Dieses Array ist am Ende aufgefüllt bis zur nächsten vollen Wortgrenze. Entladungs Codes werden in dieses Array geschrieben. Sie beginnen mit dem, der dem Hauptteil der Funktion am nächsten ist, und bewegen sich an die Ränder der Funktion. Die Bytes für jeden Entladungs Code werden in Big-Endian-Reihenfolge gespeichert, sodass Sie direkt abgerufen werden können, beginnend mit dem signifikantesten ersten Byte, das den Vorgang und die Länge des restlichen Codes identifiziert.

1. Wenn das **X** -Bit in der Kopfzeile auf 1 festgelegt wurde, wird nach dem Entladungs Code Bytes die Ausnahmehandler-Informationen angezeigt. Sie besteht aus einem einzelnen **Ausnahmehandler-RVA** , der die Adresse des Ausnahme Handlers selbst bereitstellt. Es folgt sofort eine Menge an Daten variabler Länge, die vom Ausnahmehandler benötigt wird.

Der. XData-Datensatz ist so konzipiert, dass es möglich ist, die ersten 8 Bytes abzurufen und diese zur Berechnung der vollständigen Größe des Datensatzes zu verwenden, abzüglich der Länge der folgenden Ausnahme Daten mit variabler Größe. Der folgende Code Ausschnitt berechnet die Größe des Datensatzes:

```cpp
ULONG ComputeXdataSize(PULONG *Xdata)
{
    ULONG EpilogScopes;
    ULONG Size;
    ULONG UnwindWords;

    if ((Xdata[0] >> 27) != 0) {
        Size = 4;
        EpilogScopes = (Xdata[0] >> 22) & 0x1f;
        UnwindWords = (Xdata[0] >> 27) & 0x0f;
    } else {
        Size = 8;
        EpilogScopes = Xdata[1] & 0xffff;
        UnwindWords = (Xdata[1] >> 16) & 0xff;
    }

    Size += 4 * EpilogScopes;
    Size += 4 * UnwindWords;
    if (Xdata[0] & (1 << 20)) {
        Size += 4;        // exception handler RVA
    }
    return Size;
}
```

Obwohl der Prolog und jedes Epilogcode über einen eigenen Index in die Entladungs Codes verfügen, wird die Tabelle zwischen Ihnen gemeinsam genutzt. Es ist durchaus möglich (und nicht ganz ungewöhnlich), dass Sie alle dieselben Codes gemeinsam nutzen können. (Ein Beispiel finden Sie in Beispiel 2 im Abschnitt " [Beispiele](#examples) ".) Compilerwriter sollten in diesem Fall optimiert werden, da der größte Index, der angegeben werden kann, 255 ist, was die Gesamtzahl der Entladungs Codes für eine bestimmte Funktion einschränkt.

### <a name="unwind-codes"></a>Entladungs Codes

Das Array von Entladungs Codes ist ein Pool von Sequenzen, die genau beschreiben, wie die Auswirkungen des Prologs rückgängig gemacht werden, und in derselben Reihenfolge gespeichert werden, in der die Vorgänge rückgängig gemacht werden müssen. Die Entladungs Codes können als ein kleiner Anweisungs Satz angesehen werden, der als eine Zeichenfolge von Bytes codiert ist. Wenn die Ausführung beendet ist, befindet sich die Rückgabeadresse der aufrufenden Funktion im LR-Register. Und alle nicht flüchtigen Register werden zu dem Zeitpunkt wieder hergestellt, an dem die Funktion aufgerufen wurde.

Wenn Ausnahmen immer nur innerhalb eines Funktions Texts und nie innerhalb eines Prologs oder Epilogs auftreten, ist nur eine einzige Sequenz erforderlich. Das Windows-Entladungs Modell erfordert jedoch, dass der Code innerhalb eines teilweise ausgeführten Prologs oder Epilogs entladen werden kann. Um diese Anforderung zu erfüllen, wurden die Entladungs Codes sorgfältig entworfen, sodass Sie 1:1 allen relevanten Opcodes im Prolog und Epilog eindeutig zuordnen. Dieser Entwurf hat mehrere Auswirkungen:

1. Durch zählen der Anzahl von Entladungs Codes ist es möglich, die Länge von Prolog und Epilog zu berechnen.

1. Wenn Sie die Anzahl der Anweisungen über den Anfang eines epilogesscope hinweg zählen, ist es möglich, die entsprechende Anzahl von Entladungs Codes zu überspringen. Anschließend können wir den Rest einer Sequenz ausführen, um die teilweise ausgeführte Entladung durch das Epilog abzuschließen.

1. Wenn Sie die Anzahl der Anweisungen vor dem Ende des Prologs zählen, ist es möglich, die entsprechende Anzahl von Entladungs Codes zu überspringen. Anschließend können wir den Rest der Sequenz ausführen, um nur die Teile des Prologs rückgängig zu machen, deren Ausführung abgeschlossen ist.

Die Entladungs Codes werden gemäß der folgenden Tabelle codiert. Alle Entlade Codes sind ein einzelnes/doppeltes Byte, mit Ausnahme derjenigen, die einen riesigen Stapel zuordnet. Vollständig ist 21 Entladungs Code vorhanden. Jeder Entladungs Code ordnet genau eine Anweisung im Prolog/Epilog zu, um das Entladen teilweise ausgeführter Prologe und Epilogs zu ermöglichen.

|Entladungs Code|Bits und Interpretation|
|-|-|
|`alloc_s`|000XXXXX: Zuordnen eines kleinen Stapels mit der Größe \< 512 (2 ^ 5 * 16).|
|`save_r19r20_x`|    001zzzzz: speichert \<x19, x20 > Paar bei `[sp-#Z*8]!`, vorindizierter Offset > =-248 |
|`save_fplr`|        01zzzzzz: speichert \<x29, LR > Pair bei `[sp+#Z*8]`, Offset \< = 504. |
|`save_fplr_x`|        10zzzzzz: speichert \<x29, LR > Paar bei `[sp-(#Z+1)*8]!`, vorindizierter Offset > =-512 |
|`alloc_m`|        11000xxx' xxxxxxxx: großen Stapel mit Größe \< 16K (2 ^ 11 * 16) zuordnen. |
|`save_regp`|        110010xx' xxzzzzzz: Save x (19 + #X) Pair bei `[sp+#Z*8]`, Offset \< = 504 |
|`save_regp_x`|        110011xx' xxzzzzzz: Save Pair x (19 + #X) bei `[sp-(#Z+1)*8]!`, vorindizierter Offset > =-512 |
|`save_reg`|        110100xx' xxzzzzzz: Save reg x (19 + #X) bei `[sp+#Z*8]`, Offset \< = 504 |
|`save_reg_x`|        1101010x' xxxzzzzz: Save reg x (19 + #X) bei `[sp-(#Z+1)*8]!`, vorindizierter Offset > =-256 |
|`save_lrpair`|         1101011x' xxzzzzzz: Save Pair \<x (19 + 2 * #X), LR > bei `[sp+#Z*8]`, Offset \< = 504 |
|`save_fregp`|        1101100x' xxzzzzzz: Save Pair d (8 + #X) bei `[sp+#Z*8]`, Offset \< = 504 |
|`save_fregp_x`|        1101101x' xxzzzzzz: Save Pair d (8 + #X), at `[sp-(#Z+1)*8]!`, vorindizierter Offset > =-512 |
|`save_freg`|        1101110x' xxzzzzzz: Save reg d (8 + #X) bei `[sp+#Z*8]`, Offset \< = 504 |
|`save_freg_x`|        11011110 "xxxzzzzz: Save reg d (8 + #X) bei `[sp-(#Z+1)*8]!`, vorindizierter Offset > =-256 |
|`alloc_l`|         11100000 ' xxxxxxxxxxxxxxxxxxxxxxxxxx ' xxxxxxxx: Zuordnen eines großen Stapels mit der Größe \< 256M (2 ^ 24 * 16) |
|`set_fp`|        11100001: x29 einrichten: mit: `mov x29,sp` |
|`add_fp`|        11100010 ' xxxxxxxx: Set up x29 with: `add x29,sp,#x*8` |
|`nop`|            11100011: Es ist kein Entladevorgang erforderlich. |
|`end`|            11100100: Ende des Entladungs Codes. Impliziert ret in Epilog. |
|`end_c`|        11100101: Ende des Entladungs Codes im aktuellen verketteten Bereich. |
|`save_next`|        11100110: das nächste nicht flüchtige int-oder FP-Registrierungs paar speichern. |
|`arithmetic(add)`|    11100111 "000zxxxx: Hinzufügen von Cookie reg (z) zu LR (0 = x28, 1 = SP); `add lr, lr, reg(z)` |
|`arithmetic(sub)`|    11100111 ' 001zxxxx: Sub Cookie reg (z) from LR (0 = x28, 1 = SP); `sub lr, lr, reg(z)` |
|`arithmetic(eor)`|    11100111 ' 010zxxxx: EOR LR with Cookie reg (z) (0 = x28, 1 = SP); `eor lr, lr, reg(z)` |
|`arithmetic(rol)`|    11100111 ' 0110xxxx: simulierte Anmeldung von LR mit Cookie reg (x28); xip0 = NETg x28; `ror lr, xip0` |
|`arithmetic(ror)`|    11100111 ' 100zxxxx: ROR LR with Cookie reg (z) (0 = x28, 1 = SP); `ror lr, lr, reg(z)` |
| |            11100111: xxxz-----: reserviert---- |
| |              11101xxx: reserviert für benutzerdefinierte Stapel Fälle unten nur für ASM-Routinen generiert |
| |              11101000: Benutzerdefinierter Stapel für MSFT_OP_TRAP_FRAME |
| |              11101001: Benutzerdefinierter Stapel für MSFT_OP_MACHINE_FRAME |
| |              11101010: Benutzerdefinierter Stapel für MSFT_OP_CONTEXT |
| |              11101100: Benutzerdefinierter Stapel für MSFT_OP_CLEAR_UNWOUND_TO_CALL |
| |              1111xxxx: reserviert |

In Anweisungen mit großen Werten, die mehrere Bytes abdecken, werden die wichtigsten Bits zuerst gespeichert. Mit diesem Entwurf können Sie die Gesamtgröße des Entladungs Codes in Bytes ermitteln, indem Sie nur das erste Byte des Codes suchen. Da jeder Entladungs Code genau einer Anweisung in einem Prolog oder Epilog zugeordnet ist, können Sie die Größe des Prologs oder Epilogs berechnen. Sie können vom Anfang der Sequenz bis zum Ende gehen und eine Nachschlage Tabelle oder ein ähnliches Gerät verwenden, um zu bestimmen, wie lange der entsprechende Opcode ist.

Die nach indizierte Offset Adressierung ist in einem Prolog nicht zulässig. Alle Offset Bereiche (#Z) entsprechen der Codierung der STP/Str-Adressierung mit Ausnahme von `save_r19r20_x`, wobei 248 für alle Speicherbereiche ausreichend ist (10 int-Register + 8 FP-Register + 8 Eingabe Register).

`save_next` muss einem Save for int-oder FP volatile-Registrierungs paar folgen: `save_regp`, `save_regp_x`, `save_fregp`, `save_fregp_x`, `save_r19r20_x` oder einer anderen `save_next`. Dabei wird das nächste Registerpaar beim nächsten 16-Byte-Slot in der Reihenfolge "wächst" gespeichert. Ein `save_next` verweist auf das erste FP-Registerpaar, wenn es auf den `save-next` folgt, der das letzte int-Registerpaar angibt.

Da die Größe der regulären Rückgabe-und Sprung Anweisungen gleich ist, besteht keine Notwendigkeit, dass ein getrennter `end`-Entladungs Code für Endaufruf Szenarios erforderlich ist.

`end_c` ist so konzipiert, dass nicht zusammenhängende Funktions Fragmente zu Optimierungszwecken verarbeitet werden. Ein `end_c`, das das Ende der Entladungs Codes im aktuellen Bereich anzeigt, muss von einer anderen Reihe von Entladungs Codes gefolgt werden, die mit einem echten `end` beendet wurden. Die Entladungs Codes zwischen `end_c` und `end` stellen die Prolog-Vorgänge in der übergeordneten Region ("Phantom"-Prolog) dar.  Weitere Details und Beispiele werden im folgenden Abschnitt beschrieben.

### <a name="packed-unwind-data"></a>Entpackte Entladedaten

Für Funktionen, deren Prologe und Epilogs der unten beschriebenen kanonischen Form folgen, können gepackte Entladedaten verwendet werden. Es entfällt, dass ein. XData-Datensatz vollständig benötigt wird, und reduziert die Kosten für die Bereitstellung von Entladedaten erheblich. Die kanonischen Prologe und Epilogs sind so konzipiert, dass Sie die allgemeinen Anforderungen einer einfachen Funktion erfüllen: Eine, die keinen Ausnahmehandler benötigt und deren Setup-und Beendigungs-Vorgänge in einer Standard Reihenfolge durchführt.

Das Format eines pData-Datensatzes mit gepackten Entladedaten sieht wie folgt aus:

![pData-Datensatz mit gepackten Entladungs Daten](media/arm64-exception-handling-packed-unwind-data.png ". pdata-Datensatz mit gepackten Entladedaten")

Die Felder lauten wie folgt:

- **RVA für Funktions Start** ist die 32-Bit-RVA des Starts der Funktion.
- **Flag** ist ein 2-Bit-Feld, wie oben beschrieben, mit der folgenden Bedeutung:
  - 00 = gepackte Entladedaten werden nicht verwendet. verbleibende Bits zeigen auf einen. XData-Datensatz
  - 01 = gepackte Entladedaten, die mit einem einzelnen Prolog und Epilogcode am Anfang und Ende des Bereichs verwendet werden
  - 10 = gepackte Entladedaten, die für Code ohne Prolog und Epilog verwendet werden. Nützlich zum beschreiben getrennter Funktions Segmente
  - 11 = reserviert.
- Die **Funktions Länge** ist ein 11-Bit-Feld, das die Länge der gesamten Funktion in Bytes, dividiert durch 4, bereitstellt. Wenn die Funktion größer als 8K ist, muss stattdessen ein vollständiger XData-Datensatz verwendet werden.
- Die **Frame Größe** ist ein 9-Bit-Feld, das die Anzahl der für diese Funktion zugeordneten Stapel Stapel dividiert durch 16 angibt. Funktionen, die mehr als (8K-16) Bytes an Stapel zuordnen, müssen einen vollständigen. XData-Datensatz verwenden. Sie enthält den Bereich lokale Variable, den Bereich für ausgehende Parameter, den aufgerufenen, den Bereich für int und FP und den Bereich für den Startparameter, aber den dynamischen Zuordnungs Bereich.
- **CR** ist ein 2-Bit-Flag, das angibt, ob die Funktion zusätzliche Anweisungen zum Einrichten einer Frame Kette und Zurückgeben von Links enthält:
  - 00 = nicht verkettete Funktion, \<x29, LR > Paar nicht im Stapel gespeichert wird.
  - 01 = nicht verkettete Funktion, \<LR > im Stapel gespeichert
  - 10 = reserviert;
  - 11 = verkettete Funktion, eine Store-/Auslastungs-paar-Anweisung wird im Prolog-/Epilog-\<x29, LR verwendet >
- **H** ist ein 1-Bit-Flag, das angibt, ob die Funktion die ganzzahligen Parameter Register (X0-x7) untersucht, indem Sie am Anfang der Funktion gespeichert werden. (0 = registriert keine Start Register, 1 = Häuser Register).
- **RegI** ist ein 4-Bit-Feld, das die Anzahl der nicht flüchtigen int-Register (x19-x28) angibt, die am kanonischen Stapel Speicherort gespeichert sind.
- **Regf** ist ein 3-Bit-Feld, das die Anzahl der nicht flüchtigen FP-Register (D8-D15) angibt, die am kanonischen Stapel Speicherort gespeichert sind. (Regf = 0: Es wird kein FP-Register gespeichert. Regf > 0: "Regf + 1 FP-Register" werden gespeichert). Gepackte Entladedaten können nicht für Funktionen verwendet werden, bei denen nur ein FP-Register gespeichert wird.

Kanonische Prologe, die in die Kategorien 1, 2 (ohne ausgehenden Parameter Bereich), 3 und 4 im obigen Abschnitt fallen, können durch das gepackte Entlade Format dargestellt werden.  Die Epilogs für kanonische Funktionen folgen einem ähnlichen Formular, außer **H** hat keine Auswirkung, die `set_fp`-Anweisung wird ausgelassen, und die Reihenfolge der Schritte und die Anweisungen in jedem Schritt werden im Epilog umgekehrt. Der-Algorithmus für "gepackt. XData" folgt den folgenden Schritten, die in der folgenden Tabelle beschrieben werden:

Schritt 0: Berechnen Sie die Größe der einzelnen Bereiche vorab.

Schritt 1: Speichern Sie die in int aufgerufenen gespeicherten Register.

Schritt 2: Dieser Schritt ist für Typ 4 in den frühen Abschnitten spezifisch. LR wird am Ende des int-Bereichs gespeichert.

Schritt 3: Speichert die vom FP aufgerufenen gespeicherten Register.

Schritt 4: Speichern Sie die Eingabeargumente im Startparameter Bereich.

Schritt 5: Weisen Sie den verbleibenden Stapel zu, einschließlich lokaler Bereiche, \<x29, LR > Pair und Bereich für ausgehende Parameter. 5a entspricht dem kanonischen Typ 1. 5B und 5C sind für den kanonischen Typ 2. 5D und 5E sind für Typ 3 und Typ 4.

Schritt #|Flagwerte|Anzahl von Anweisungen|Opcode|Entladungs Code
-|-|-|-|-
0|||`#intsz = RegI * 8;`<br/>`if (CR==01) #intsz += 8; // lr`<br/>`#fpsz = RegF * 8;`<br/>`if(RegF) #fpsz += 8;`<br/>`#savsz=((#intsz+#fpsz+8*8*H)+0xf)&~0xf)`<br/>`#locsz = #famsz - #savsz`|
1|0 < **RegI** < = 10|REGI/2 + **RegI** %2|`stp x19,x20,[sp,#savsz]!`<br/>`stp x21,x22,[sp,#16]`<br/>`...`|`save_regp_x`<br/>`save_regp`<br/>`...`
2|**CR**==01*|1|`str lr,[sp,#(intsz-8)]`\*|`save_reg`
3|0 < **regf** < = 7|(Regf + 1)/2 +<br/>(Regf + 1) %2)|`stp d8,d9,[sp,#intsz]`\*\*<br/>`stp d10,d11,[sp,#(intsz+16)]`<br/>`...`<br/>`str d(8+RegF),[sp,#(intsz+fpsz-8)]`|`save_fregp`<br/>`...`<br/>`save_freg`
4|**H** == 1|4|`stp x0,x1,[sp,#(intsz+fpsz)]`<br/>`stp x2,x3,[sp,#(intsz+fpsz+16)]`<br/>`stp x4,x5,[sp,#(intsz+fpsz+32)]`<br/>`stp x6,x7,[sp,#(intsz+fpsz+48)]`|`nop`<br/>`nop`<br/>`nop`<br/>`nop`
5a|**CR** == 11 && #locsz<br/> < = 512|2|`stp x29,lr,[sp,#-locsz]!`<br/>`mov x29,sp`\*\*\*|`save_fplr_x`<br/>`set_fp`
5 b|**CR** == 11 &&<br/>512 < #locsz <= 4080|3|`sub sp,sp,#locsz`<br/>`stp x29,lr,[sp,0]`<br/>`add x29,sp,0`|`alloc_m`<br/>`save_fplr`<br/>`set_fp`
5C|**CR** == 11 && #locsz > 4080|4|`sub sp,sp,4080`<br/>`sub sp,sp,#(locsz-4080)`<br/>`stp x29,lr,[sp,0]`<br/>`add x29,sp,0`|`alloc_m`<br/>`alloc_s`/`alloc_m`<br/>`save_fplr`<br/>`set_fp`
5D|(**CR** == 00 \|\| **CR**==01) &&<br/>#locsz <= 4080|1|`sub sp,sp,#locsz`|`alloc_s`/`alloc_m`
5e|(**CR** == 00 \|\| **CR**==01) &&<br/>#locsz > 4080|2|`sub sp,sp,4080`<br/>`sub sp,sp,#(locsz-4080)`|`alloc_m`<br/>`alloc_s`/`alloc_m`

\*, wenn **CR** = = 01 und **RegI** eine ungerade Zahl ist, werden Schritt 2 und Last save_rep in Schritt 1 zu einem save_regp zusammengeführt.

\* @ no__t-1 Wenn **RegI** == **CR** = = 0 und **regf** ! = 0, führt die erste STP für den Gleit Komma Wert für die prädekrement.

\* @ no__t-1 @ no__t-2 im Epilog ist keine Anweisung vorhanden, die `mov x29,sp` entspricht. Gepackte Entladedaten können nicht verwendet werden, wenn eine Funktion eine Wiederherstellung von SP von x29 erfordert.

### <a name="unwinding-partial-prologs-and-epilogs"></a>Entwickeln von partiellen Prologe und Epilogs

Die häufigste entlockende Situation ist eine, bei der die Ausnahme oder der Rückruf im Hauptteil der Funktion aufgetreten ist, und nicht im Prolog und allen Epilogs. In dieser Situation ist das Entladen ganz einfach: der Entlader beginnt einfach mit dem Ausführen der Codes im Entlade Array, beginnend bei Index 0 und wird fortgesetzt, bis ein endopcode erkannt wird.

Es ist schwieriger, in dem Fall, in dem eine Ausnahme oder ein Interrupt auftritt, beim Ausführen eines Prologs oder Epilogs ordnungsgemäß entladen zu werden. In diesen Fällen wird der Stapel Rahmen nur teilweise konstruiert. Das Problem besteht darin, genau zu bestimmen, was geschehen ist, um es ordnungsgemäß rückgängig zu machen.

Nehmen Sie z. b. diese Prolog-und Epilogsequenz an:

```asm
0000:    stp    x29,lr,[sp,#-256]!          // save_fplr_x  256 (pre-indexed store)
0004:    stp    d8,d9,[sp,#224]             // save_fregp 0, 224
0008:    stp    x19,x20,[sp,#240]           // save_regp 0, 240
000c:    mov    x29,sp                      // set_fp
         ...
0100:    mov    sp,x29                      // set_fp
0104:    ldp    x19,x20,[sp,#240]           // save_regp 0, 240
0108:    ldp    d8,d9,[sp,224]              // save_fregp 0, 224
010c:    ldp    x29,lr,[sp],#256            // save_fplr_x  256 (post-indexed load)
0110:    ret    lr                          // end
```

Neben jedem Opcode ist der passende Entlade Code, der diesen Vorgang beschreibt. Sie können sehen, wie die Reihe von Entladungs Codes für den Prolog ein genaues Spiegelbild der Entladungs Codes für das Epilogcode ist (ohne die abschließende Anweisung des Epilogcode). Es ist eine gängige Situation, weshalb wir immer annehmen, dass die Entladungs Codes für den Prolog in umgekehrter Reihenfolge in der Ausführungsreihenfolge des Proxys gespeichert werden.

Für Prolog und Epilog haben wir also einen gemeinsamen Satz von Entladungs Codes:

`set_fp`, `save_regp 0,240`, `save_fregp,0,224`, `save_fplr_x_256`, `end`

Der Epilogcode-Fall ist einfach, da er in normaler Reihenfolge ist. Beginnend bei Offset 0 innerhalb des Epilogcode (der bei Offset 0x100 in der Funktion beginnt), wird erwartet, dass die vollständige Entlade Sequenz ausgeführt wird, da noch kein Bereinigung durchgeführt wurde. Wenn wir uns eine Anweisung in (am Offset 2 im Epilog) befinden, können wir den ersten Entladungs Code überspringen. Wir können diese Situation generalisieren und annehmen, dass eine 1:1-Zuordnung zwischen Opcodes und Entladungs Codes vorliegt. Um mit der Entladung von Anweisung *n* im Epilog zu beginnen, sollten die ersten *n* Entladungs Codes übersprungen und die Ausführung von dort aus begonnen werden.

Es stellt sich heraus, dass eine ähnliche Logik für den Prolog funktioniert, außer in umgekehrter Reihenfolge. Wenn wir mit der Auflösung von Offset 0 im Prolog beginnen, möchten wir nichts ausführen. Wenn wir von Offset 2 entladen, bei dem es sich um eine Anweisung in handelt, möchten wir mit der Ausführung der Entlade Sequenz beginnen. (Beachten Sie, dass die Codes in umgekehrter Reihenfolge gespeichert werden.) Und auch hier können wir generalisieren: Wenn wir mit der Entladung von Anweisung n im Prolog beginnen, sollten Sie mit der Ausführung von n Entladungs Codes am Ende der Liste der Codes beginnen.

Es ist nicht immer der Fall, dass die Prolog-und epilogcodes exakt übereinstimmen. Aus diesem Grund muss das Entlade Array möglicherweise mehrere Codesequenzen enthalten. Verwenden Sie die folgende Logik, um den Offset für den Beginn der Verarbeitung von Codes zu ermitteln:

1. Wenn das Entladen aus dem Hauptteil der Funktion ausgeführt wird, beginnen Sie mit dem Ausführen von Entladungs Codes bei Index 0, und fahren Sie fort, bis Sie den Opcode "End" erreichen.

1. Wenn Sie in einem Epilogcode entwickeln, verwenden Sie den epilogspezifischen Start Index, der mit dem epilogbereich bereitgestellt wird, als Ausgangspunkt. Berechnen Sie, wie viele Bytes der betreffende PC vom Anfang des Epilog ist. Fahren Sie dann mit den Entladungs Codes fort, und überspringen Sie Entladungs Codes, bis alle bereits ausgeführten Anweisungen berücksichtigt werden. Führen Sie ab diesem Punkt den Befehl aus.

1. Wenn Sie im Prolog eine Entwickelung durchführen, verwenden Sie Index 0 als Ausgangspunkt. Berechnen Sie die Länge des Prolog-Codes aus der Sequenz, und berechnen Sie dann, wie viele Bytes der betreffende PC am Ende des Prologs liegt. Fahren Sie dann mit den Entladungs Codes fort, und überspringen Sie Entladungs Codes, bis alle noch nicht ausgeführten Anweisungen berücksichtigt werden. Führen Sie ab diesem Punkt den Befehl aus.

Diese Regeln bedeuten, dass die Entladungs Codes für den Prolog immer der erste im Array sein müssen. Und Sie sind auch die Codes, die verwendet werden, um beim Entladen innerhalb des Texts zu entladen. Alle epilogspezifischen Codesequenzen sollten unmittelbar nach befolgt werden.

### <a name="function-fragments"></a>Funktions Fragmente

Aus Gründen der Codeoptimierung und anderen Gründen ist es möglicherweise besser, eine Funktion in getrennte Fragmente aufzuteilen (auch als "Regionen" bezeichnet). Wenn Split, erfordert jedes resultierende Funktions Fragment einen eigenen, separaten pData-Datensatz (und möglicherweise. XData).

Für jedes getrennte sekundäre Fragment, das über einen eigenen Prolog verfügt, wird erwartet, dass keine Stapel Anpassung im Prolog erfolgt. Sämtlicher Stapel Speicher, der für eine sekundäre Region erforderlich ist, muss von der übergeordneten Region (oder dem sogenannten Host Bereich) vorab zugeordnet werden. Dies sorgt dafür, dass die Stapelzeiger Bearbeitung strikt im ursprünglichen Prolog der Funktion durchführt.

Ein typischer Fall von Funktions Fragmenten ist "Code Trennung" mit diesem Compiler kann einen Code Bereich aus seiner Host Funktion verschieben. Es gibt drei ungewöhnliche Fälle, die durch die Trennung von Code verursacht werden könnten.

#### <a name="example"></a>Beispiel

- (Region 1: Anfang)

    ```asm
        stp     x29,lr,[sp,#-256]!      // save_fplr_x  256 (pre-indexed store)
        stp     x19,x20,[sp,#240]       // save_regp 0, 240
        mov     x29,sp                  // set_fp
        ...
    ```

- (Region 1: Ende)

- (Region 3: Anfang)

    ```asm
        ...
    ```

- (Region 3: Ende)

- (Region 2: Anfang)

    ```asm
        ...
        mov     sp,x29                  // set_fp
        ldp     x19,x20,[sp,#240]       // save_regp 0, 240
        ldp     x29,lr,[sp],#256        // save_fplr_x  256 (post-indexed load)
        ret     lr                      // end
    ```

- (Region 2: Ende)

1. Nur Prolog (Region 1: alle Epilogs befinden sich in getrennten Regionen):

   Nur der Prolog muss beschrieben werden. Dies kann nicht im Compact. pdata-Format dargestellt werden. Im vollständigen. XData-Fall kann der Wert durch Festlegen von Epilog count = 0 dargestellt werden. Siehe Region 1 im obigen Beispiel.

   Entladungs Codes: `set_fp`, `save_regp 0,240`, `save_fplr_x_256`, `end`.

1. Nur Epilogs (Region 2: Prolog befindet sich in der Host Region)

   Es wird davon ausgegangen, dass beim springen in diesen Bereich alle Prolog Codes ausgeführt wurden. Eine Teilentladung kann in Epilogs auf dieselbe Weise erfolgen wie in einer normalen Funktion. Diese Art von Region kann nicht durch Compact. pdata dargestellt werden. Im vollständigen. XData-Datensatz kann er mit einem "Phantom"-Prolog codiert werden, der durch ein Entladungs Code paar von `end_c` und `end` in Klammern eingeschlossen wird.  Der führende `end_c` gibt an, dass die Größe des Prologs NULL ist. Der Epilogcode-Start Index des einzelnen Epilogcode verweist auf `set_fp`.

   Entladungs Code für Region 2: `end_c`, `set_fp`, `save_regp 0,240`, `save_fplr_x_256`, `end`.

1. Es sind keine Prologe oder Epilogs (Region 3: Prologe und alle Epilogs in anderen Fragmenten):

   Das Compact. pdata-Format kann über das Setting-Flag = 10 angewendet werden. Mit vollständigem. XData-Datensatz, epilogcount = 1. Der Entladungs Code ist mit dem oben aufgeführten Code für Region 2 identisch, aber der Epilog-Start Index verweist auch auf `end_c`. Eine Teilentladung erfolgt in diesem Bereich des Codes nie.

Ein weiterer komplizierterer Fall von Funktions Fragmenten ist "Verkleinerung verkleinern". Der Compiler kann das Speichern von aufgerufenen gespeicherten Registern bis außerhalb des Prologs der Funktions Einträge verzögern.

- (Region 1: Anfang)

    ```asm
        stp     x29,lr,[sp,#-256]!      // save_fplr_x  256 (pre-indexed store)
        stp     x19,x20,[sp,#240]       // save_regp 0, 240
        mov     x29,sp                  // set_fp
        ...
    ```

- (Region 2: Anfang)

    ```asm
        stp     x21,x22,[sp,#224]       // save_regp 2, 224
        ...
        ldp     x21,x22,[sp,#224]       // save_regp 2, 224
    ```

- (Region 2: Ende)

    ```asm
        ...
        mov     sp,x29                  // set_fp
        ldp     x19,x20,[sp,#240]       // save_regp 0, 240
        ldp     x29,lr,[sp],#256        // save_fplr_x  256 (post-indexed load)
        ret     lr                      // end
    ```

- (Region 1: Ende)

Im Prolog von Region 1 wird der Stapel Speicher vorab zugeordnet. Sie sehen, dass Region 2 denselben Entlade Code hat, auch wenn Sie aus der Host Funktion heraus verschoben wird.

Region 1: `set_fp`, `save_regp 0,240`, `save_fplr_x_256`, `end` mit dem Epilog-Start Index zeigt auf `set_fp` wie üblich.

Region 2: `save_regp 2, 224`, `end_c`, `set_fp`, `save_regp 0,240`, `save_fplr_x_256`, `end`. Epilog Start Index zeigt auf den ersten Entladungs Code `save_regp 2, 224`.

### <a name="large-functions"></a>Große Funktionen

Fragmente können verwendet werden, um Funktionen zu beschreiben, die größer sind als der von den Bitfeldern im. XData-Header festgelegten Grenzwert von 1 m. Um eine sehr große Funktion wie diese zu beschreiben, muss Sie in Fragmente unterteilt werden, die kleiner als 1 Mio. sind. Jedes Fragment sollte so angepasst werden, dass es kein Epilogcode in mehrere Teile unterteilt.

Nur das erste Fragment der Funktion enthält einen Prolog. alle anderen Fragmente sind so gekennzeichnet, dass Sie keinen Prolog haben. Abhängig von der Anzahl der vorhandenen Epilogs kann jedes Fragment 0 (null) oder mehr Epilogs enthalten. Beachten Sie, dass jeder epilogbereich in einem Fragment seinen Start Offset relativ zum Anfang des Fragments angibt, nicht den Anfang der Funktion.

Wenn ein Fragment keinen Prolog und kein Epilog hat, erfordert es weiterhin einen eigenen. pdata-Datensatz (und möglicherweise. XData), um zu beschreiben, wie der Vorgang innerhalb des Funktions Texts entladen werden soll.

## <a name="examples"></a>Beispiele

### <a name="example-1-frame-chained-compact-form"></a>Beispiel 1: Frame verkettet, Compact-Form

```asm
|Foo|     PROC
|$LN19|
    str     x19,[sp,#-0x10]!        // save_reg_x
    sub     sp,sp,#0x810            // alloc_m
    stp     fp,lr,[sp]              // save_fplr
    mov     fp,sp                   // set_fp
                                    //  end of prolog
    ...

|$pdata$Foo|
    DCD     imagerel     |$LN19|
    DCD     0x416101ed
    ;Flags[SingleProEpi] functionLength[492] RegF[0] RegI[1] H[0] frameChainReturn[Chained] frameSize[2080]
```

### <a name="example-2-frame-chained-full-form-with-mirror-prolog--epilog"></a>Beispiel 2: Frame verkettetes, vollständiges Formular mit Spiegel Prolog & Epilog

```asm
|Bar|     PROC
|$LN19|
    stp     x19,x20,[sp,#-0x10]!    // save_regp_x
    stp     fp,lr,[sp,#-0x90]!      // save_fplr_x
    mov     fp,sp                   // set_fp
                                    // end of prolog
    ...
                                    // begin of epilog, a mirror sequence of Prolog
    mov     sp,fp
    ldp     fp,lr,[sp],#0x90
    ldp     x19,x20,[sp],#0x10
    ret     lr

|$pdata$Bar|
    DCD     imagerel     |$LN19|
    DCD     imagerel     |$unwind$cse2|
|$unwind$Bar|
    DCD     0x1040003d
    DCD     0x1000038
    DCD     0xe42291e1
    DCD     0xe42291e1
    ;Code Words[2], Epilog Count[1], E[0], X[0], Function Length[6660]
    ;Epilog Start Index[0], Epilog Start Offset[56]
    ;set_fp
    ;save_fplr_x
    ;save_r19r20_x
    ;end
```

Der Epilog-Start Index [0] verweist auf dieselbe Sequenz von Prolog-Entlade Code.

### <a name="example-3-variadic-unchained-function"></a>Beispiel 3: Nicht verkettete Variadic-Funktion

```asm
|Delegate| PROC
|$LN4|
    sub     sp,sp,#0x50
    stp     x19,lr,[sp]
    stp     x0,x1,[sp,#0x10]        // save incoming register to home area
    stp     x2,x3,[sp,#0x20]        // ...
    stp     x4,x5,[sp,#0x30]
    stp     x6,x7,[sp,#0x40]        // end of prolog
    ...
    ldp     x19,lr,[sp]             // beginning of epilog
    add     sp,sp,#0x50
    ret     lr

    AREA    |.pdata|, PDATA
|$pdata$Delegate|
    DCD     imagerel |$LN4|
    DCD     imagerel |$unwind$Delegate|

    AREA    |.xdata|, DATA
|$unwind$Delegate|
    DCD     0x18400012
    DCD     0x200000f
    DCD     0xe3e3e3e3
    DCD     0xe40500d6
    DCD     0xe40500d6
    ;Code Words[3], Epilog Count[1], E[0], X[0], Function Length[18]
    ;Epilog Start Index[4], Epilog Start Offset[15]
    ;nop        // nop for saving in home area
    ;nop        // ditto
    ;nop        // ditto
    ;nop        // ditto
    ;save_lrpair
    ;alloc_s
    ;end
```

Der Epilog-Start Index [4] verweist auf die Mitte des Prolog-Entlade Codes (teilweise wieder verwenden des Entlade Arrays).

## <a name="see-also"></a>Siehe auch

[Übersicht über ARM64 ABI-Konventionen](arm64-windows-abi-conventions.md)<br/>
[ARM-Ausnahmebehandlung](arm-exception-handling.md)
