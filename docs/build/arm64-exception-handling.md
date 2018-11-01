---
title: ARM64-Ausnahmebehandlung
ms.date: 07/11/2018
ms.openlocfilehash: 82775a61adf8437565b5bb691716451b225e72e4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50620596"
---
# <a name="arm64-exception-handling"></a>ARM64-Ausnahmebehandlung

Windows auf ARM64 verwendet das gleiche strukturierte Ausnahmebehandlung Mechanismus für die asynchrone Hardware generierten – Ausnahmen als auch synchrone Software generierte Ausnahmen. Sprachspezifische Ausnahmehandler werden auf von Windows strukturierter Ausnahmebehandlung mithilfe von Sprachhilfsfunktionen erstellt. Dieses Dokument beschreibt die Behandlung von Ausnahmen in Windows auf ARM64 und die sprachhilfen, die von Code, der von der Microsoft-ARM-Assembler- und Visual C++-Compiler generiert wird verwendet.

## <a name="goals-and-motivation"></a>Ziele und motivation

Die Ausnahme entladen Daten Konventionen und diese Beschreibung, dienen zum:

1. Geben Sie genügend Beschreibung, um zuzulassen, ohne Code, Tests in allen Fällen entladen.

   - Analyse des Codes muss der Code in ausgelagert werden. Dies verhindert, dass Sie entladen, in einigen Fällen, in denen es empfiehlt sich (Ablaufverfolgung, Erstellen von Stichproben, Debuggen).

   - Analyse des Codes ist komplexer. der Compiler muss sorgfältig nur Anweisungen zu generieren, der Entlader decodieren kann.

   - Wenn entladen nicht durch die Verwendung von entladungscodes ausführlich erläutert werden, müssen Sie dann in einigen Fällen zum Decodieren der Anweisung zurückgegriffen. Dies erhöht die Komplexität und im Idealfall würden vermieden werden kann.

1. Unterstützung, die Entladung im Prolog der Mid "und" Mid Epilog.

   - Entladen von mehr als die Ausnahmebehandlung in Windows verwendet wird, daher ist es wichtig, dass wir ausführen kann eine exakte entladen, selbst wenn in der Mitte eine Codesequenz Prolog- oder Epilogcode.

1. Dauern Sie, bis eine minimale Menge an Speicherplatz.

   - Die entladungscodes müssen nicht aggregieren, um die binäre Größe erheblich zu erhöhen.

   - Da die entladungscodes voraussichtlich im Arbeitsspeicher gesperrt werden, gewährleistet ein geringen Ressourcenbedarf einen minimalen Mehraufwand für jede Binärdatei geladen.

## <a name="assumptions"></a>Annahmen

Hierbei handelt es sich um die Annahmen, die in der Beschreibung für die Ausnahmebehandlung:

1. Prologe und Epiloge neigen dazu, um entweder andere zu spiegeln. Von der Nutzung der dieses Merkmal "common" kann die Größe der Metadaten erforderlich, um die Beschreibung der Entladung erheblich reduziert werden. Im Text der Funktion spielt es keine Rolle, ob der Prolog-Vorgänge rückgängig gemacht werden werden, oder der Epilog-in einem nach vorn gerichtete Weise Vorgänge. Beides sollte zum gleichen Ergebnis führen.

1. Funktionen sind für das gesamte eher relativ klein sein. Verschiedene Optimierungen für Speicherplatz nutzen diese um die effizienteste Packen von Daten zu erzielen.

1. Es ist keine bedingter Code in epilogen.

1. Dedizierte Framezeigerregister: Wenn die sp in einem anderen Register (R29 entwickelt bei) im Prolog gespeichert wird, registrieren, die bleibt unverändert, während die Funktion, sodass der ursprüngliche sp jederzeit wiederhergestellt werden kann.

1. Es sei denn, der gespeicherten Prozedur in einem anderen Register gespeichert wird, tritt ein, alle Manipulation des Stapelzeigers ausschließlich innerhalb der Prolog und Epilog.

1. Die stapelrahmenlayout werden organisiert, wie im nächsten Abschnitt beschrieben.

## <a name="arm64-stack-frame-layout"></a>Stapelrahmenlayout bei ARM64

![stapelrahmenlayout](../build/media/arm64-exception-handling-stack-frame.png "stapelrahmenlayout")

Für Funktionen der Frame verkettet kann das fp-Lr-Paar an beliebiger Position in der lokalen Variablen Bereich je nach der Optimierung Überlegungen gespeichert werden. Das Ziel ist, um die Anzahl der lokalen Variablen zu maximieren, die von einer einzelnen Anweisung, die basierend auf Frame-Pointer (R29 entwickelt bei) oder der Stapelzeiger (sp) erreicht werden kann. Jedoch für `alloca` Funktionen, er verkettet werden muss und R29 entwickelt bei muss am Ende Stack verweisen. Für eine bessere Abdeckung von Register-Paar-Adressierung-Modus nicht flüchtig registrieren, damit Aave, Bereiche am oberen Rand der LAN-Stack positioniert werden. Hier sind Beispiele, die einige der am effizientesten Prolog Sequenzen zu veranschaulichen. Aus Gründen der Übersichtlichkeit und besseren Ort des Caches aufweist die Reihenfolge der aufgerufenen gespeicherten Register speichern, in dem alle kanonischen Prologe "immer größer werdenden einrichten" Reihenfolge. `#framesz` unten können Sie die Größe des gesamten Stapels (außer ' Alloca-Bereich) darstellt. `#localsz` und `#outsz` LAN-Größe zu kennzeichnen (einschließlich des Speichervorgangs Bereich für die \<R29 entwickelt bei, Lr > Paar) und der Parametergröße bzw. ausgehende.

1. Verkettet, #localsz < = 512

    ```asm
        stp    r19,r20,[sp,-96]!        // pre-indexed, save in 1st FP/INT pair
        stp    d8,d9,[sp,16]            // save in FP regs (optional)
        stp    r0,r1,[sp,32]            // home params (optional)
        stp    r2,r3,[sp, 48]
        stp    r4,r5,[sp,64]
        stp    r6,r7,[sp,72]
        stp    r29, lr, [sp, -#localsz]!    // save <r29,lr> at bottom of local area
        mov    r29,sp                   // r29 points to bottom of local
        sub    sp, #outsz               // (optional for #outsz != 0)
    ```

1. Verkettet, #localsz > 512

    ```asm
        stp    r19,r20,[sp,-96]!        // pre-indexed, save in 1st FP/INT pair
        stp    d8,d9,[sp,16]            // save in FP regs (optional)
        stp    r0,r1,[sp,32]            // home params (optional)
        stp    r2,r3,[sp, 48]
        stp    r4,r5,[sp,64]
        stp    r6,r7,[sp,72]
        sub    sp,#localsz+#outsz       // allocate remaining frame
        stp    r29, lr, [sp, #outsz]    // save <r29,lr> at bottom of local area
        add    r29,sp, #outsz           // setup r29 points to bottom of local area
    ```

1. Nicht verkettete, Funktionen (Lr nicht gespeichert)

    ```asm
        stp    r19,r20,[sp, -72]!       // pre-indexed, save in 1st FP/INT reg-pair
        stp    r21,r22,[sp, 16]
        str    r23 [sp,32]
        stp    d8,d9,[sp,40]            // save FP regs (optional)
        stp    d10,d11,[sp,56]
        sub    sp,#framesz-72           // allocate the remaining local area
    ```

   Alle lokalen erfolgt basierend auf SP. \<R29 entwickelt bei, Lr > verweist auf den vorherigen Frame. Für die Größe des Quellframes < = 512, die "sub sp,..." können wegoptimiert werden, wenn der Bereich Regs gespeichert am unteren Rand der Stapel verschoben wird. Der Nachteil dieser ist, dass es ist nicht konsistent mit anderer Layouts, die oben genannten, gespeicherten Regs nehmen Sie Teil des Bereichs für das Paar-Regs und vor und nach dem indizierten Offset Adressierung.

1. Nicht verkettete nichtblatt-Funktionen (Int, gespeichert im Bereich wird Lr gespeichert)

    ```asm
        stp    r19,r20,[sp,-80]!        // pre-indexed, save in 1st FP/INT reg-pair
        stp    r21,r22,[sp,16]          // ...
        stp    r23, lr,[sp, 32]         // save last Int reg and lr
        stp    d8,d9,[sp, 48]           // save FP reg-pair (optional)
        stp    d10,d11,[sp,64]          // ...
        sub    sp,#framesz-80           // allocate the remaining local area
    ```

   Oder mit einer geraden Anzahl gespeichert Int-Register,

    ```asm
        stp    r19,r20,[sp,-72]!        // pre-indexed, save in 1st FP/INT reg-pair
        stp    r21,r22,[sp,16]          // ...
        str    lr,[sp, 32]              // save lr
        stp    d8,d9,[sp, 40]           // save FP reg-pair (optional)
        stp    d10,d11,[sp,56]          // ...
        sub    sp,#framesz-72           // allocate the remaining local area
    ```

   Nur r19 gespeichert:

    ```asm
        sub    sp, sp, #16              // reg save area allocation*
        stp    r19,lr,[sp,0]            // save r19, lr
        sub    sp,#framesz-16           // allocate the remaining local area
    ```

   \* Das Reg speichern Bereich Zuordnung ist nicht in die stp reduziert, da eine stp bereits indizierten Reg-Lr nicht mit den entladungscodes dargestellt werden kann.

   Alle lokalen erfolgt basierend auf SP. \<R29 entwickelt bei > verweist auf den vorherigen Frame.

1. Verkettet, #framesz < = 512, #outsz = 0

    ```asm
        stp    r29, lr, [sp, -#framesz]!    // pre-indexed, save <r29,lr>
        mov    r29,sp                       // r29 points to bottom of stack
        stp    r19,r20,[sp, #framesz -32]   // save INT pair
        stp    d8,d9,[sp, #framesz -16]     // save FP pair
    ```

   Mit der oben genannten #1-Prolog verglichen, liegt der Vorteil, dass alle Register speichern Anweisungen werden direkt nach dem Zuordnen von Anweisung nur einen Stapel ausgeführt werden können. Es besteht daher keine Anti-Abhängigkeit auf sp, die von der Anweisung auf Parallelität verhindert.

1. Verkettet, frame-Größe > 512 (optional für die Funktionen ohne Alloca)

    ```asm
        stp    r29, lr, [sp, -80]!          // pre-indexed, save <r29,lr>
        stp    r19,r20,[sp,16]              // save in INT regs
        stp    r21,r22,[sp,32]              // ...
        stp    d8,d9,[sp,48]                // save in FP regs
        stp    d10,d11,[sp,64]
        mov    r29,sp                       // r29 points to top of local area
        sub    sp,#framesz-80               // allocate the remaining local area
    ```

   Für die Optimierung Zweck können R29 entwickelt bei an einer beliebigen Position in der Nähe zu der eine bessere Abdeckung vor/nach-indexed Offset Adressierungsmodus für "Reg-Paar" platziert werden. "Lokal", unter der Frame-Pointer können zugegriffen werden basierend auf SP.

1. Verkettet, Rahmengröße > 4K, mit oder ohne alloca(),

    ```asm
        stp    r29, lr, [sp, -80]!          // pre-indexed, save <r29,lr>
        stp    r19,r20,[sp,16]              // save in INT regs
        stp    r21,r22,[sp,32]              // ...
        stp    d8,d9,[sp,48]                // save in FP regs
        stp    d10,d11,[sp,64]
        mov    r29,sp                       // r29 points to top of local area
        mov    r8, #framesz/16
        bl     chkstk
        sub    sp, r8*16                    // allocate remaining frame
                                            // end of prolog
        ...
        sp = alloca                         // more alloca() in body
        ...
                                            // beginning of epilog
        mov    sp,r29                       // sp points to top of local area
        ldp    d10,d11, [sp,64],
        ...
        ldp    r29, lr, [sp], -80           // post-indexed, reload <r29,lr>
    ```

## <a name="arm64-exception-handling-information"></a>Informationen zur Behandlung von ARM64 Ausnahme

### <a name="pdata-records"></a>.pdata-Datensätze

Die .pdata-Datensätze sind ein geordnetes Array von Elementen mit fester Länge die in einer PE-Binärdatei jede stapelbearbeitungsfunktion beschreiben. Beachten Sie sorgfältig, den Ausdruck "Stack-bearbeiten": Leaf-Funktionen, die aber keine lokalen Speicher und keine benötigen, können Sie nicht flüchtigen Register gespeichert/wiederhergestellt, erfordern keine .pdata-Datensatz; Diese sollten explizit ausgelassen werden, um Platz zu sparen. Eine Entladung aus einer dieser Funktionen erhalten einfach die Rückgabeadresse aus LR, an den Aufrufer nach oben zu verschieben.

Jeder .pdata-Datensatz für ARM64 ist 8 Byte lang. Das allgemeine Format für jeden Datensatz stellen die 32-Bit-RVA der Funktion zu starten, in das erste Wort, gefolgt von einer Sekunde, enthält entweder einen Zeiger auf eine Variable Länge .xdata-Block oder ein gepacktes Wort, das eine Funktion (kanonisch) entladen Sequenz zu beschreiben.

![.pdata-Datensatzlayout](../build/media/arm64-exception-handling-pdata-record.png ".pdata-Datensatz-Layout")

Die Felder sind wie folgt aus:

- **Funktion RVA starten** ist die 32-Bit-RVA des Starts der Funktion.

- **Flag** ist ein 2-Bit-Feld, wie Sie die verbleibenden 30 Bit des zweiten .pdata-Worts zu interpretieren angibt. Wenn **Flag** 0 ist, dann bilden die verbleibenden bits eine **Ausnahme Informationen RVA** (mit der die beiden niedrigsten Bitwerte implizit 0). Wenn **Flag** ungleich NULL ist, ist, dann bilden die verbleibenden bits eine **gepackte Entladedaten Daten** Struktur.

- **Ausnahme Informationen RVA** ist die Adresse der variabler Länge, die Struktur für Ausnahmeinformationen, im Abschnitt .xdata gespeichert. Diese Daten müssen 4-Bytes ausgerichtet sein.

- **Gepackte Entladedaten Daten** ist eine komprimierte Beschreibung der Vorgänge zum Entladen von einer Funktion, wenn eine kanonische Form. In diesem Fall ist kein .xdata-Datensatz erforderlich.

### <a name="xdata-records"></a>.XData-Datensätze

Wenn das gepackte Entladeformat nicht zur Beschreibung der Entladung einer Funktion ausreicht, muss ein .xdata-Datensatz mit variabler Länge erstellt werden. Die Adresse dieses Datensatzes wird im zweiten Wort des .pdata-Datensatzes gespeichert. Das Format von .xdata ist eine gepackte variabler Länge, die Gruppe von Wörtern an:

![.XData-Datensatzlayout](../build/media/arm64-exception-handling-xdata-record.png ".xdata-Datensatz-Layout")

Diese Daten ist in vier Abschnitte unterteilt:

1. Eine 1 oder 2-Wort-Header, der die Gesamtgröße der Struktur beschreibt und wichtige Funktionsdaten bereitstellen. Das zweite Worte ist nur vorhanden, wenn sowohl die **Epilog Anzahl** und **Code Wörter** Felder werden auf 0 festgelegt. Dies sind die Bitfelder im Header:

   a. **Länge-Funktion** ist ein 18-Bit-Feld, der angibt, der der Gesamtlänge der Funktion in Bytes geteilt durch 4. Wenn eine Funktion größer als 1 Million ist, müssen mehrere Pdata und Xdata-Einträge verwendet werden, um die Funktion zu beschreiben. Finden Sie unter den [umfangreiche Funktionen](#large-functions) finden Sie weitere Details.

   b. **Vers** ist ein 2-Bit-Feld, das die Version der verbleibenden Xdata. Während ich dies schreibe, nur Version 0 definiert ist, und Werte von 1 bis 3 sind daher nicht zulässig.

   c. **X** ist ein 1-Bit-Feld, der angibt, das Vorhandensein (1) oder fehlen (0) von Ausnahmedaten.

   d. **E** ist ein Bitfeld gibt an, dass die Informationen, die einen einzelnen Epilog in den Header (1 steckt) statt, erfordern zusätzliche Bereich beschreibt höher (0) Wörter.

   e. **Anzahl der Epilog** ist ein 5-Bit-Feld mit zwei Bedeutungen, abhängig vom Zustand **E** Bit:

      1. Wenn **E** auf 0 festgelegt ist: Es gibt die Anzahl der Gesamtzahl von ausnahmebereichen, die in Abschnitt 2 beschriebene an. Wenn mehr als 31 Bereiche in der Funktion vorhanden sind und dann die **Code Wörter** Feld muss auf 0 festgelegt werden, um anzugeben, dass ein ausnahmewort erforderlich ist.

      2. Wenn **E** auf 1 festgelegt ist, und klicken Sie dann dieses Feld gibt den Index des ersten entladungscodes an, die die und nur Epilog beschreibt.

   f. **Code Wörter** ist ein 5-Bit-Feld, der angibt, die Anzahl der 32-Bit-Wörter, die erforderlich sind, die alle entladungscodes in Abschnitt 4 enthält. Wenn mehr als 31 Wörter erforderlich sind (d. h. maximal 124 entladen Codebytes), und klicken Sie dann dieses Feld auf 0 festgelegt werden muss, um anzugeben, dass ein ausnahmewort erforderlich ist.

   g. **Erweitert die Anzahl der Epilog** und **erweiterte Code Wörter** sind Felder 16-Bit- und 8-Bit-bzw., mehr Speicherplatz für die Codierung einer ungewöhnlich großen Anzahl von epilogen bereitstellen oder eine ungewöhnlich große Anzahl von entladen Code Wörter. Das erweiterungswort, enthält dieser Felder ist nur vorhanden, wenn beide die **Epilog Anzahl** und **Code Wörter** Felder im ersten headerwort werden auf 0 festgelegt.

1. Nach den Ausnahmedaten Wenn **Epilog Anzahl** ist nicht 0 (null), ist eine Liste mit Informationen über Bereiche des Epilogs, um ein Wort gepackt und in der Reihenfolge zunehmender startoffsets gespeichert. Jeder Bereich enthält die folgenden Bits:

   a. **Epilog starten Offset** ist ein 18-Bit-Feld, die den Offset in Bytes geteilt durch 4, der relativ zum Start der Funktion Epilog beschreibt.

   b. **Res** ist ein 4-Bit-Feld, das für zukünftige Erweiterungen reserviert. Sein Wert muss 0 sein.

   c. **StartIndex Epilog** ein 10-Bit (2 Weitere Bits als **erweiterte Code Wörter**), der angibt, des Byte-Indexes des ersten Felds entladungscode, der diesen Epilog beschreibt.

1. Nachdem die Liste der Epilog Bereiche ein Array von Bytes, die entladungscodes enthalten wird, werden in einem späteren Abschnitt ausführlich beschrieben. Dieses Array ist am Ende aufgefüllt bis zur nächsten vollen Wortgrenze. Die Bytes werden in Little-Endian-Reihenfolge gespeichert, sodass sie im Little-Endian-Modus direkt abgerufen werden können.

1. Nach den entladungscodebytes (und, wenn die **X** Bit im Header auf 1 festgelegt wurde) wird die ausnahmehandlerinformationen. Dies besteht aus einer einzelnen **Ausnahme-Handler RVA** die Adresse des ausnahmehandlers selbst bereitstellen und unmittelbar danach ein variabler Länge, die Menge der Daten, die vom Ausnahmehandler erforderlich.

Die oben genannten .xdata-Datensatz ist so entworfen, dass es möglich ist, den ersten 8 Bytes abzurufen, und berechnen aus, die die volle Größe des Datensatzes (abzüglich der Länge von die Ausnahmedaten mit variabler Größe, die folgt). Der folgende Codeausschnitt berechnet die Datensatzgröße:

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

Beachten Sie, dass obwohl der Prolog und jeder Epilog hat einen eigenen Index in den entladungscodes, in der Tabelle genutzt gemeinsam und es ist durchaus möglich, dass (und nicht ganz selten), die sie die gleichen Codes gemeinsam verwenden können (siehe Beispiel 2 in Anhang A unten). Compiler-Autoren sollten für diesen Fall insbesondere optimieren, da der größte Index, der angegeben werden können, 255, ist daher beschränken die Gesamtzahl der entladungscodes für eine bestimmte Funktion.

### <a name="unwind-codes"></a>Entladungscodes

Das Array an entladungscodes ist sequenzenpool, der genau, wie die Auswirkungen der Prolog, in der Reihenfolge rückgängig machen beschreibt, in denen die Vorgänge rückgängig gemacht werden müssen. Die entladungscodes können als ein Satz von minianweisungen, als eine Zeichenfolge von Bytes codiert betrachtet werden. Wenn die Ausführung abgeschlossen ist, an die aufrufende Funktion die Rückgabeadresse im Lr-Register ist, und alle nicht flüchtigen Register werden auf die Werte zurückgesetzt, zu dem Zeitpunkt, der die Funktion aufgerufen wurde.

Wenn Ausnahmen garantiert immer nur innerhalb einer Funktion (und nicht mit einem Prolog oder jeder Epilog) ausgeführt wurden, klicken Sie dann wäre nur eine einzigen Sequenz erforderlich. Windows-entlademodell erfordert jedoch, dass es innerhalb eines teilweise ausgeführten Prologs oder Epilogs aus zu entladen werden. Um diese Anforderungen zu erfüllen, wurden die entladungscodes sorgfältig entworfen, dass sie eindeutig 1:1 zu jedem relevanten Opcode im Prolog und Epilog zugeordnet. Das hat eine Reihe von Auswirkungen:

1. Durch zählen der Anzahl von entladungscodes, ist es möglich, die die Länge der Prolog und Epilog zu berechnen.

1. Durch zählen der Anzahl von Anweisungen nach dem Start eines Bereichs Epilog, es ist möglich, die gleiche Anzahl von entladungscodes zu überspringen, und führen den Rest einer Sequenz in die teilweise ausgeführte abgeschlossen entladen wird, dass der Epilog durchgeführt wurde.

1. Durch zählen der Anzahl von Anweisungen vor dem Ende der Prolog, ist es möglich, die gleiche Anzahl von entladungscodes zu überspringen, und führen den Rest der Sequenz, die nur die Teile des Prologs rückgängig zu machen, die Ausführung abgeschlossen ist.

Gemäß der folgenden Tabelle werden die entladungscodes codiert wird. Alle entladungscodes sind eine einzelne/Doppelbyte, mit Ausnahme der, die einen großen Stapel zuordnet. Es sind völlig 21 entladungscode. Jede Entladung Code Maps genau eine Anweisung in die Prolog-und Epilogcode um für die Entladung teilweise ausgeführter Prologe und Epiloge zu ermöglichen.

Entladungscode|Bits und interpretation
|-|-|
`alloc_s`|000xxxxx: Zuordnen von kleinen Stapel mit Größe < 512 (2 ^ 5 * 16).
`save_r19r20_x`|    001zzzzz: Speichern \<r19, r20 > an [sp-#Z * 8]!, vorab indizierte Offset > =-248
`save_fplr`|        01zzzzzz: Speichern \<R29 entwickelt bei, Lr > gekoppelt werden am [sp + #Z * 8], Offset < = 504.
`save_fplr_x`|        10zzzzzz: Speichern \<R29 entwickelt bei, Lr > gekoppelt werden am [sp-(#Z + 1) * 8]!, vorab indizierte Offset > =-512
`alloc_m`|        bis jetzt 11000xxx\|Xxxxxxxx: große Stack mit einer Größe von 16 KB < zuordnen (2 ^ 11 * 16).
`save_regp`|        110010xx\|Xxzzzzzz: Speichern von r(19+#X)-Paar an [sp + #Z * 8], Offset < = 504
`save_regp_x`|        110011xx\|Xxzzzzzz: Speichern von Paar r(19+#X) am [sp-(#Z + 1) * 8]!, vorab indizierte Offset > =-512
`save_reg`|        110100xx\|Xxzzzzzz: Speichern Sie die Reg-r(19+#X) am [sp + #Z * 8], Offset < = 504
`save_reg_x`|        1101010 X\|Xxxzzzzz: Speichern Sie die Reg-r(19+#X) am [sp-(#Z + 1) * 8]!, vorab indizierte Offset > =-256
`save_lrpair`|         1101011 X\|Xxzzzzzz: Speichern von Paar \<r19 + 2 *#X, Lr > am [sp + #Z*8], Offset < = 504
`save_fregp`|        1101100 X\|Xxzzzzzz: Speichern von Paar d(8+#X) am [sp + #Z * 8], Offset < = 504
`save_fregp_x`|        1101101 X\|Xxzzzzzz: Speichern Sie Paar d(8+#X), [sp-(#Z + 1) * 8]!, vorab indizierte Offset > =-512
`save_freg`|        1101110 X\|Xxzzzzzz: Speichern Sie die Reg-d(8+#X) am [sp + #Z * 8], Offset < = 504
`save_freg_x`|        11011110\|Xxxzzzzz: Speichern Sie die Reg-d(8+#X) am [sp-(#Z + 1) * 8]!, vorab indizierte Offset > =-256
`alloc_l`|         11100000\|Xxxxxxxx\|Xxxxxxxx\|Xxxxxxxx: große Stack mit einer Größe von 256 M < zuordnen (2 ^ 24 * 16)
`set_fp`|        11100001: Richten Sie R29 entwickelt bei: mit: R29 entwickelt bei Mov, sp
`add_fp`|        11100010\|Xxxxxxxx: R29 entwickelt bei mit einrichten: Hinzufügen von R29 entwickelt bei, sp, #x * 8
`nop`|            11100011: keine Entladung Vorgang erforderlich ist.
`end`|            11100100: Ende der entladungscodes. Impliziert ret im Epilog.
`end_c`|        11100101: Ende entladungscode im aktuellen verketteten Bereich.
`save_next`|        11100110: Speichern des nächsten nicht flüchtigen Int oder FP registrieren Paar.
`arithmetic(add)`|    11100111\| 000zxxxx: Lr Cookie reg(z) hinzugefügt (0 = X28, 1 = sp); Hinzufügen von Lr, Lr, reg(z)
`arithmetic(sub)`|    11100111\| 001zxxxx: sub-Cookie reg(z) von Lr (0 = X28, 1 = sp); sub-Lr "," Lr "," reg(z)
`arithmetic(eor)`|    11100111\| 010zxxxx: Eor Lr mit Cookie reg(z) (0 = X28, 1 = sp); Eor Lr, Lr, reg(z)
`arithmetic(rol)`|    11100111\| 0110xxxx: simulierten Rol von Lr mit Cookie Reg (x28); xip0 = Neg X28; Ror Lr, xip0
`arithmetic(ror)`|    11100111\| 100zxxxx: Ror Lr mit Cookie reg(z) (0 = X28, 1 = sp); Ror Lr, Lr, reg(z)
||            11100111: Xxxz---: – reserviert
||              11101xxx: reserviert für benutzerdefinierte Stack folgenden Anwendungsfälle generiert nur für Asm-Routinen
||              11101001: benutzerdefinierte Stack für MSFT_OP_TRAP_FRAME
||              11101010: benutzerdefinierte Stack für MSFT_OP_MACHINE_FRAME
||              11101011: benutzerdefinierte Stack für MSFT_OP_CONTEXT
||              1111xxxx: reservierte

In Anweisungen mit großen Werten umfassen mehrere Bytes werden die höchstwertigen Bits zuerst gespeichert werden. Die oben genannten entladungscodes sind so entworfen, dass durch das erste Byte des Codes einfach überprüfen, kennen die Gesamtgröße in Bytes des entladungscodes möglich ist. Angesichts der Tatsache, dass jede entladungscode genau eine Anweisung in Prolog-und Epilogcode zugeordnet ist, um die Größe der Prolog oder Epilog berechnen muss erfolgen lediglich, ab dem Anfang der Sequenz durchlaufen, bis zum Ende, eine Nachschlagetabelle oder ähnliches Gerät verwenden, um zu bestimmen, wie lange der cor reagiert Opcode ist.

Beachten Sie, dass nach dem indizierten Offset Adressierung im Prolog nicht zulässig ist. Alle Offset Bereiche (#Z) entsprechen, die Codierung der STP/STR-Adressierung, mit Ausnahme von `save_r19r20_x` in welche 248 ausreichend ist für alle Bereiche (10 Int-Register + 8 FP-Register + 8 Eingabe Register) zu speichern.

`save_next` Führen Sie einen Speichervorgang für Int oder FP Volatile registrieren Paar müssen: `save_regp`, `save_regp_x`, `save_fregp`, `save_fregp_x`, `save_r19r20_x`, oder einen anderen `save_next`. Nächste Register-Paar an die nächste 16-Byte-Slot in der Reihenfolge "wachsende einrichten" gespeichert. `save-next` nach einem `save_next` , das das letzte Int-Register-Paar bezieht sich auf die ersten Paar der FP-Register bezeichnet.

Da die Größe der regulären zurückkehren und springen Anweisungen identisch sind, besteht keine Notwendigkeit, der eine getrennte `end` entladungscode Endeaufruf-Szenarien.

`end_c` Dient zum Behandeln von nicht zusammenhängenden funktionsfragmente zu Optimierungszwecken. Ein `end_c` gibt an das Ende des entladungscodes im aktuellen Bereich muss durch eine andere Reihe von entladungscodes endete mit einem echten folgen `end`. Die entladungscodes zwischen `end_c` und `end` Prolog Vorgänge im übergeordneten Bereich ("phantom" Prolog) darstellen.  Weitere Informationen und Beispiele werden im Abschnitt unten beschrieben.

### <a name="packed-unwind-data"></a>Gepackte Entladedaten

Für Funktionen, deren prologen und epilogen folgen, die die kanonische Form im folgenden beschrieben gepackt, entladen Daten verwendet werden können, entfällt ein .xdata-Datensatz vollständig und erheblich reduzieren die Kosten der Bereitstellung Entladung der Daten. Den kanonischen prologen und epilogen sollen die Anforderungen der allgemeinen einer einfachen Funktion, die einen Ausnahmehandler nicht erfordert, und die Setup- und Beendigungsfunktionen Vorgänge in der standardmäßigen Reihenfolge ausführt.

Das Format eines .pdata-Datensatzes mit gepackte Entladedaten Daten sieht wie folgt aus:

![.pdata-Datensatz mit gepackte Entladedaten](../build/media/arm64-exception-handling-packed-unwind-data.png ".pdata-Datensatz mit gepackte Entladedaten")

Die Felder sind wie folgt aus:

- **Funktion RVA starten** ist die 32-Bit-RVA des Starts der Funktion.
- **Flag** ist ein 2-Bit-Feld, wie oben beschrieben, die folgende Bedeutung:
  - 00 = gepackte Entladedaten nicht verwendet. Verbleibende Bits zeigen auf .xdata-Datensatz, unten
  - 01 = gepackte Entladedaten verwendet werden, wie unten beschrieben, mit einzelnen Prolog und Epilog am Anfang und Ende des Bereichs
  - 10 = gepackte Entladedaten verwendet werden, wie unten beschrieben, für Code ohne Prolog- und Epilog; Dies ist nützlich, wenn getrennte Funktion Segmente.
  - 11 = reserviert.
- **Länge-Funktion** ist ein 11-Bit-Feld, das die Länge der gesamten Funktion in Bytes geteilt durch 4 bereitstellt. Wenn die Funktion größer als 8 KB ist, muss stattdessen ein voller .xdata-Datensatz verwendet werden.
- **Frame-Größe** ist ein 9-Bit-Feld, der angibt, der Anzahl der Bytes vom Stapel, der für diese Funktion, geteilt durch 16 zugeordnet ist. Funktionen, die größer als (8 KB – 16) Bytes an Stapelspeicher reservieren müssen einen vollständiger .xdata-Datensatz verwenden. Dies schließt die lokale Variable Bereich ausgehende Eingabeaufforderungsbereich für Parameter vom aufgerufenen gespeicherten Int und FP-Bereich und home Parameterbereich aus, jedoch ohne die dynamische Zuordnung Bereich.
- **CR** ist ein 2-Bit-Flag gibt an, ob die Funktion zusätzliche Anweisungen zum Einrichten einer rahmenkette und die return-Link schließt:
  - 00 = nicht verkettete Funktion \<R29 entwickelt bei, Lr > Paar nicht im Stapel gespeichert.
  - 01 = nicht verkettete Funktion \<Lr > wird im Stapel gespeichert
  - 10 = reserviert.
  - 11 = verketteten-Funktion eine Store/Load-Paar-Anweisung wird verwendet, in die Prolog-und Epilogcode \<R29 entwickelt bei, Lr >
- **H** ist ein 1-Bit-Flag gibt an, ob die Funktion der herausgreift registriert (r0-r7), indem sie am Anfang der Funktion zu speichern. (0 = Register nicht heraus, 1 = greift Register).
- **RegI** ist ein 4-Bit-Feld, der angibt, der Anzahl der nicht flüchtigen INT-Register (r19-r28) in den kanonischen Stapelspeicherort gespeichert.
- **RegF** ist ein 3-Bit-Feld, der angibt, der Anzahl der nicht flüchtigen FP-Register (d8-d15) in den kanonischen Stapelspeicherort gespeichert. (0 = kein FP Register gespeichert wird, m > 0: m + 1 FP-Register gespeichert). Für die Funktion, speichern Sie nur ein FP-Register, die gepackte Entladedaten nicht die Daten angewendet werden.

Kanonischen Prologe, die in Kategorien 1, 2 (ohne ausgehenden Eingabeaufforderungsbereich für Parameter), 3 und 4 im obigen Abschnitt fallen können durch gepackte entladeformat dargestellt werden.  Mit Ausnahme von der epilogen für kanonische Funktionen sehr ähnlichen Form, führen Sie **H** hat keine Auswirkungen, die `set_fp` Anweisung ausgelassen wird, und die Reihenfolge der Schritte sowie Anweisungen in den einzelnen Schritten im Epilog umgekehrt werden. Der Algorithmus für gepackte Xdata: Diese Schritte aus, in der folgenden Tabelle beschrieben

Dies ist Schritt 0: Führen Sie die erforderliche Berechnung der Größe der einzelnen Bereiche.

Schritt 1: Speichern Sie Int aufgerufenen gespeicherten Register.

Schritt 2: Dieser Schritt ist für Typ 4 in den frühen Abschnitten. LR wird am Ende der Int-Bereich gespeichert.

Schritt 3: Speichern Sie FP aufgerufenen gespeicherten Register.

Schritt 4: Speichern Sie input-Argumente in der private Bereich.

Schritt 5: Zuordnen der verbleibenden Stapel, einschließlich LAN, \<R29 entwickelt bei, Lr > Kopplung und der ausgehende Eingabeaufforderungsbereich für Parameter. 5a entspricht kanonischen Typs 1. 5 und 5c sind für kanonische Typ 2. 5D und 5e für beide Typ 3 und 4 geben.

Schritt #|Flagwerte|Anzahl von Anweisungen|Opcode|Entladungscode
-|-|-|-|-
0|||`#intsz = RegI * 8;`<br/>`if (CR==01) #intsz += 8; // lr`<br/>`#fpsz = RegF * 8;`<br/>`if(RegF) #fpsz += 8;`<br/>`#savsz=((#intsz+#fpsz+8*H)+0xf)&~0xf)`<br/>`#locsz = #famsz - #savsz`|
1|0 < **regI** < = 10|RegI / 2 + **RegI** % 2|`stp r19,r20,[sp,#savsz]!`<br/>`stp r21,r22,[sp,16]`<br/>`...`|`save_regp_x`<br/>`save_regp`<br/>`...`
2|**CR**== 01 *|1|`str lr,[sp, #intsz-8]`\*|`save_reg`
3|0 < **RegF** < = 7|(RegF + 1) / 2 +<br/>(RegF + 1) % 2).|`stp d8,d9,[sp, #intsz]`\*\*<br/>`stp d10,d11,[sp, #intsz+16]`<br/>`...`<br/>`str d(8+RegF),[sp, #intsz+#fpsz-8]`|`save_fregp`<br/>`...`<br/>`save_freg`
4|**H** == 1|4|`stp r0,r1,[sp, #intsz+#fpsz]`<br/>`stp r2,r3,[sp, #intsz+#fpsz+16]`<br/>`stp r4,r5,[sp, #intsz+#fpsz+32]`<br/>`stp r6,r7,[sp, #intsz+#fpsz+48]`|`nop`<br/>`nop`<br/>`nop`<br/>`nop`
5a|**CR** == 11 & & #locsz<br/> < = 512|2|`stp r29,lr,[sp,-#locsz]!`<br/>`mov r29,sp`\*\*\*|`save_fplr_x`<br/>`set_fp`
5 b|**CR** == 11 &AMP; &AMP;<br/>512 < #locsz < = 4088|3|`sub sp,sp, #locsz`<br/>`stp r29,lr,[sp,0]`<br/>`add r29, sp, 0`|`alloc_m`<br/>`save_fplr`<br/>`set_fp`
5c|**CR** == 11 & & #locsz > 4088|4|`sub sp,sp,4088`<br/>`sub sp,sp, (#locsz-4088)`<br/>`stp r29,lr,[sp,0]`<br/>`add r29, sp, 0`|`alloc_m`<br/>`alloc_s`/`alloc_m`<br/>`save_fplr`<br/>`set_fp`
5D|(**CR** == 00 \| \| **CR**== 01) &AMP; &AMP;<br/>#locsz < = 4088|1|`sub sp,sp, #locsz`|`alloc_s`/`alloc_m`
5e|(**CR** == 00 \| \| **CR**== 01) &AMP; &AMP;<br/>#locsz > 4088|2|`sub sp,sp,4088`<br/>`sub sp,sp, (#locsz-4088)`|`alloc_m`<br/>`alloc_s`/`alloc_m`

\*: Bei **CR** == 01 und **RegI** eine ungerade Zahl ist, Schritt2 und letzten Save_rep in Schritt 1 in einem Save_regp zusammengeführt werden.

\*\* Wenn **RegI** == **CR** == 0 (null) und **RegF** ! = 0 ist, das erste stp aus, für die Gleitkommazahlen der prädekrement ist.

\*\*\* Keine Anweisung entspricht `mov r29, sp` im Epilog vorhanden ist. Wenn für die Wiederherstellung der sp von R29 entwickelt bei eine Funktion erforderlich ist, wir können gepackt Entladung der Daten.

### <a name="unwinding-partial-prologs-and-epilogs"></a>Entladung teilweise prologen und epilogen

Die am häufigsten verwendete Entladung Situation ist eine aufgetreten ist, in dem die Ausnahme oder der Aufruf im Hauptteil der Funktion von Prolog und allen epilogen. In diesem Fall entladen ist unkompliziert: der Entlader einfach beginnt mit der Ausführung von Codes in der Entladung-Array, beginnend bei Index 0 und fortsetzen, bis ein endopcode festgestellt wird.

Es ist schwieriger, in dem Fall ordnungsgemäß entladen, in dem eine Ausnahme oder ein Interrupt tritt auf, während der Ausführung von einem Prolog oder Epilog. Klicken Sie in diesen Fällen der Stapelrahmen nur teilweise erstellt wird, und der Trick besteht darin zu bestimmen, genau ausgeführt wurden um korrekt rückgängig machen.

Führen Sie beispielsweise diese Prolog und Epilog-Sequenz:

```asm
0000:    stp    r29, lr, [sp, -256]!        // save_fplr_x  256 (pre-indexed store)
0004:    stp    d8,d9,[sp,224]              // save_fregp 0, 224
0008:    stp    r19,r20,[sp,240]            // save_regp 0, 240
000c:    mov    r29,sp                      // set_fp
         ...
0100:    mov    sp,r29                      // set_fp
0104:    ldp    r19,r20,[sp,240]            // save_regp 0, 240
0108:    ldp    d8,d9,[sp,224]              // save_fregp 0, 224
010c:    ldp    r29, lr, [sp, -256]!        // save_fplr_x  256 (post-indexed load)
0110:    ret     lr                         // end
```

Neben jedem Opcode befindet sich der entsprechende entladungscode, der diesen Vorgang beschreibt. Die erste, was zu beachten ist, dass die Reihe von entladungscodes für den Prolog eine genaue Gegenstück, der die entladungscodes für den Epilog (ohne Berücksichtigung der letzten Anweisung des Epilogs). Dies ist eine gängige Situation, und aus diesem Grund die Entladung Codes für den Prolog sind immer davon ausgegangen, dass von Ausführungsreihenfolge für den Prolog in umgekehrter Reihenfolge gespeichert werden.

Daher sind für den Prolog und Epilog, einen gemeinsamen Satz an entladungscodes bleibt:

`set_fp`, `save_regp 0,240`, `save_fregp,0,224`, `save_fplr_x_256`, `end`

Ab der Epilog-Fall (Weitere einfache unverändert in der normalen Reihenfolge), bei Offset 0 im Epilog (die am Offset 0 x 100 in der Funktion startet), würden wir erwarten, dass führen Sie die volle entladesequenz aus, da noch keine Bereinigung vorgenommen wurde. Wenn wir uns einer Anweisung (am Offset 2 im Epilog) finden, können wir erfolgreich entladen, durch den ersten entladungscodes zu überspringen. Diese Situation zu verallgemeinern, vorausgesetzt eine 1:1-Zuordnung von Opcodes und entladungscodes, wir können angeben, wenn wir von n der Anweisung im Epilog entladen werden, wir sollten die ersten n entladungscodes zu überspringen und von dort ausführen.

Es stellt sich heraus, dass für die funktioniert mit einer ähnlichen Logik für den Prolog, außer in umgekehrter Reihenfolge. Wenn wir die Entladung von Offset 0 im Prolog sind, möchten wir nichts ausgeführt. Wenn wir bei Offset 2, Entladen der einer Anweisung ist, dann sollten wir Starten der Ausführung der Entladung Sequenz einen entladungscode vom Ende (Beachten Sie, dass die Codes in umgekehrter Reihenfolge gespeichert werden). Und hier auch wir können generalisieren, wenn wir die Entladung von Anweisung n im Prolog sind, wir beginnen sollten, n entladungscodes vom Ende der Liste der Codes ausführen.

Jetzt ist es nicht immer der Fall, den der Prolog und Epilog Codes exakt übereinstimmen. Aus diesem Grund müssen die Entladung Array Reihe von Codesequenzen enthalten. Um den Offset, an dem Beginn der Verarbeitungscodes zu bestimmen, verwenden Sie die folgende Logik:

1. Wenn die Entladung wird der Text der Funktion, einfach beginnt die Ausführung der entladungscodes bei Index 0, und weiterhin bis zum Erreichen eines "End"-OpCodes.

1. Wenn innerhalb eines Epilogs aus zu entladen, verwenden Sie den Startindex Epilog-spezifische, durch den Bereich der Epilog als Ausgangspunkt bereitgestellt. Berechnen Sie, wie viele Bytes sich der betreffende PC vom Beginn des Epilogs ist. Klicken Sie dann fahren fort, um vorwärts durch die entladungscodes, entladungscodes überspringen, bis alle bereits ausgeführten Anweisungen einbezogen sind. Führen Sie dann die zu diesem Zeitpunkt gestartet.

1. Wenn der Prolog Entladung, verwenden Sie Index 0, als Ausgangspunkt. Berechnen Sie die Länge der Prolog-Code aus der Sequenz zu, und klicken Sie dann zu berechnen Sie, wie viele Bytes sich der betreffende PC am Ende der Prolog ist. Klicken Sie dann fahren fort, um vorwärts durch die entladungscodes, entladungscodes überspringen, bis alle noch nicht ausgeführten Anweisungen einbezogen sind. Führen Sie dann die zu diesem Zeitpunkt gestartet.

Regeln, die entladungscodes für den Prolog müssen immer sein kann, die zuerst im Array, und sie sind auch in der allgemeinen Groß-/Kleinschreibung entladen aus im Text entladen verwendeten Codes. Sequenzen Epilog-spezifischen Code sollte unmittelbar folgen.

### <a name="function-fragments"></a>Funktionsfragmente

Optimierungszwecken Code und anderer Gründe kann es besser, eine Funktion in getrennten Fragmente (auch als "Regionen" bezeichnet) aufgeteilt sein. Wenn dies abgeschlossen ist, erfordert jedes resultierende funktionsfragment einen eigenen .pdata-Datensatz (und möglicherweise xdata) Datensatz.

Für getrennten sekundären Fragment, das über eine eigene Prolog verfügt, wird davon ausgegangen, dass keine stapelanpassungen gibt in der Prolog durchgeführt wird. Alle stack Speicherplatz vom sekundären Regionen müssen vorab von dessen übergeordneter Bereich (oder aufgerufenen Host-Region) zugeordnet werden. Auf diese Weise Zeiger stapelbearbeitung ausschließlich im ursprünglichen Prolog der Funktion.

Ein typischer Fall von funktionsfragmenten ist "Trennung von code" mit die der Compiler möglicherweise einen Codebereich aus der Host-Funktion verschoben. Es gibt drei ungewöhnliche Fälle, die durch die codetrennung geführt werden konnte.

#### <a name="example"></a>Beispiel:

- (die Region 1: Starten)

    ```asm
        stp     r29, lr, [sp, -256]!    // save_fplr_x  256 (pre-indexed store)
        stp     r19,r20,[sp,240]        // save_regp 0, 240
        mov     r29,sp                  // set_fp
        ...
    ```

- (die Region 1: End)
- (die Region 3: Starten)

    ```asm
        ...
    ```

- (die Region 3: End)
- (die Region 2: Starten)

    ```asm
    ...
        mov     sp,r29                  // set_fp
        ldp     r19,r20,[sp,240]        // save_regp 0, 240
        ldp     r29, lr, [sp, -256]!    // save_fplr_x  256 (post-indexed load)
        ret     lr                      // end
    ```

- (die Region 2: End)

1. Nur Prolog (Region 1: alle epilogen befinden sich in getrennten Regionen):

   Es muss nur der Prolog beschrieben werden. Dies kann durch kompakten .pdata-Format dargestellt werden. Bei voller .xdata kann dies durch Festlegen der Anzahl der Epilog dargestellt werden = 0. Finden Sie in Region 1 im obigen Beispiel.

   Entladungscodes: `set_fp`, `save_regp 0,240`, `save_fplr_x_256`, `end`.

1. Nur epilogen (Region-2: Prolog im Host-Bereich ist)

   Es wird vorausgesetzt, das Time-Steuerelement, das in dieser Region, alle Prolog-Codes ausgeführt wurden. Teilweise Entladung kann die gleiche Weise wie eine normale Funktion im epilogen auftreten. Diese Art von Region kann nicht durch kompakten .pdata dargestellt werden. Im vollständigen Xdata-Datensatz, können Sie mit einer "phantom" Prolog, die in Klammern durch codiert eine `end_c` und `end` Entladen von Code-Paar.  Das führende `end_c` gibt an, die Größe der Prolog ist 0 (null). Epilog Startindex des einzelnen Epilog verweist auf die `set_fp`.

   Entladungscode für die Region 2: `end_c`, `set_fp`, `save_regp 0,240`, `save_fplr_x_256`, `end`.

1. Kein prologen und epilogen (Region 3: prologen und epilogen mit allen befinden sich in anderen Fragmenten):

   Kompakten .pdata-Format angewendet werden kann, über das Festlegen von Kennzeichen = 10. Mit voller .xdata-Datensatz, Epilog Count = 1. Entladedaten-Code ist identisch mit denen für die Region 2 oben, jedoch Epilog startIndex verweist auch auf `end_c`. Teilweise Entladung wird in dieser Region des Codes nicht passieren dürfen.

Ein weiterer komplizierter Fall von funktionsfragmenten ist "Verkleinern von Wrapping" mit die der Compiler möglicherweise verzögert Speicherung vom aufgerufenen gespeicherten Register bis außerhalb des Funktionsprologs-Eintrag.

- (die Region 1: Starten)

    ```asm
        stp     r29, lr, [sp, -256]!    // save_fplr_x  256 (pre-indexed store)
        stp     r19,r20,[sp,240]        // save_regp 0, 240
        mov     r29,sp                  // set_fp
        ...
    ```

- (die Region 2: Starten)

    ```asm
        stp     r21,r22,[sp,224]        // save_regp 2, 224
        ...
        ldp     r21,r22,[sp,224]        // save_regp 2, 224
    ```

- (die Region 2: End)

    ```asm
        ...
        mov     sp,r29                  // set_fp
        ldp     r19,r20,[sp,240]        // save_regp 0, 240
        ldp     r29, lr, [sp, -256]!    // save_fplr_x  256 (post-indexed load)
        ret     lr                      // end
    ```

- (die Region 1: End)

Im Prolog der Region 1 wird Stapelspeicher vorab zugeordnet. Beachten Sie, dass diese Region 2 den gleichen Code für die Entladung aufweisen, die, den auch sie aus der Host-Funktion verschoben wird.

Region 1: `set_fp`, `save_regp 0,240`, `save_fplr_x_256`, `end` mit Epilog startIndex zeigt auf `set_fp` wie gewohnt.

Region-2: `save_regp 2, 224`, `end_c`, `set_fp`, `save_regp 0,240`, `save_fplr_x_256`, `end`. StartIndex Epilog verweist, um den Code zunächst entladen `save_regp 2, 224`.

### <a name="large-functions"></a>Umfangreiche Funktionen

Fragmente können genutzt werden, um Funktionen, die größer als die 1 Million-Grenze von den Bit-Feldern im .xdata-Header zu beschreiben. Um eine sehr große Funktion wie folgt zu beschreiben, muss sie einfach in Fragmente kleiner als 1 Million unterteilt werden. Jedes Fragment sollte angepasst werden, so dass es einen Epilog nicht in mehrere Stücke aufgeteilt wird.

Nur das erste Fragment der Funktion enthält einen Prolog. Alle anderen Fragmente werden als müssen keinen Prolog markiert. Abhängig von der Anzahl von epilogen vorhanden kann jedes Fragment NULL oder mehr epilogen enthalten. Bedenken Sie, dass jeder Epilog-Bereich in einem Fragment dessen Startoffset relativ zum Start des Fragments und nicht dem Start der Funktion angibt.

Wenn ein Fragment keinen Prolog und keine Epilog hat, erfordert er dennoch einen eigenen .pdata-Datensatz (und möglicherweise xdata) Datensatz zum Entladen von innerhalb des Texts der Funktion beschrieben.

## <a name="examples"></a>Beispiele

### <a name="example-1-frame-chained-compact-form"></a>Beispiel 1: Frame verkettet, Compact-Formular

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

### <a name="example-2-frame-chained-full-form-with-mirror-prolog--epilog"></a>Beispiel 2: Frame verkettet, Full Form mit Spiegelung Prolog und Epilog

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

Beachten Sie, dass die gleiche Sequenz von Prolog-entladungscodes EpilogStart Index [0] verweist.

### <a name="example-3-variadic-unchained-function"></a>Beispiel 3: Variadic nicht die Funktion verkettet.

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

Hinweis: EpilogStart Index [4] verweist, in die Mitte des Prolog-entladungscodes (teilweise Wiederverwendung Entladung Array).

## <a name="see-also"></a>Siehe auch

[Übersicht über die ARM64-ABI-Konventionen](arm64-windows-abi-conventions.md)<br/>
[ARM-Ausnahmebehandlung](../build/arm-exception-handling.md)
