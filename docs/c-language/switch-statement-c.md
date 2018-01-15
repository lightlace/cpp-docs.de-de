---
title: switch-Anweisung (C) | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: switch
dev_langs: C++
helpviewer_keywords: switch keyword [C]
ms.assetid: fbede014-23bd-4ab1-8094-c8d9d9cb963a
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 84594f668d0fc807ebb815cc519c7d45f62e8b12
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="switch-statement-c"></a>switch-Anweisung (C)
Die Anweisungen `switch` und **case** dienen dem Steuern von komplexen bedingten und Branchvorgängen. Mit der `switch`-Anweisung wird die Steuerung an eine Anweisung innerhalb des Texts übergeben.  
  
## <a name="syntax"></a>Syntax  
 *selection-statement*:  
 **switch (** *expression* **)** *statement*  
  
 *labeled-statement*:  
 **case** *constant-expression* **:** *statement*  
  
 **default :** *statement*  
  
 Die Steuerung wird an die Anweisung übergeben, deren **case** *constant-expression* dem Wert von **switch (** *expression* **)** entspricht. Die `switch`-Anweisung kann eine beliebige Anzahl von **case**-Instanzen enthalten. Es können aber keine zwei case-Konstanten in der gleichen `switch`-Anweisung denselben Wert haben. Die Ausführung des Anweisungstexts beginnt bei der ausgewählten Anweisung und wird bis zum Ende des Texts fortgesetzt oder bis eine **break**-Anweisung die Steuerung aus dem Text übergibt.  
  
 Die Verwendung der `switch`-Anweisung sieht in etwa folgendermaßen aus:  
  
 `switch` (*expression*)  
  
 **{**  
  
 *Deklarationen*  
  
 sein.  
  
 sein.  
  
 .  
  
 **case** *constant-expression* **:**  
  
 *ausgeführte Anweisungen, wenn der Ausdruck dem*  
  
 *Wert dieses konstanten Ausdrucks entspricht*  
  
 sein.  
  
 sein.  
  
 sein.  
  
 **break;**  
  
 **default:**  
  
 *ausgeführte Anweisungen, wenn der Ausdruck*  
  
 *keinem "case constant-expression" entspricht*  
  
 **}**  
  
 Sie können mit der **break**-Anweisung die Verarbeitung eines bestimmten Falls innerhalb der `switch`-Anweisung beenden und bis zum Ende der `switch`-Anweisung branchen. Ohne **break** wird das Programm mit dem nächsten Fall fortgesetzt, und die Anweisungen werden bis zu einer **break**-Anweisung oder dem Ende der Anweisung ausgeführt. In einigen Situationen ist diese Fortsetzung wünschenswert.  
  
 Die **default**-Anweisung wird ausgeführt, wenn kein **case** *constant-expression* dem Wert von **switch (** *expression* **)** entspricht. Wenn die **default**-Anweisung ausgelassen und keine **case**-Übereinstimmung gefunden wird, wird keine der Anweisungen im `switch`-Text ausgeführt. Es kann höchstens eine **default**-Anweisung geben. Die **default**-Anweisung muss nicht am Ende stehen. Sie kann überall im Text der `switch`-Anweisung vorkommen. Eine **case**- oder **default**-Bezeichnung kann nur innerhalb einer `switch`-Anweisung angezeigt werden.  
  
 Der Typ des `switch` *expression* und des **case** *constant-expression* müssen ganzzahlig sein. Der Wert von jedem **case** *constant-expression* muss innerhalb des Anweisungstexts eindeutig sein.  
  
 Die **case**- und **default**-Bezeichnungen des `switch`-Anweisungstexts sind nur im ersten Test wichtig, in dem bestimmt wird, an welcher Stelle des Anweisungstexts die Ausführung beginnt. Switch-Anweisungen können geschachtelt werden. Alle statischen Variablen werden vor dem Ausführen in einer `switch`-Anweisung initialisiert.  
  
> [!NOTE]
>  Deklarationen können am Anfang der Verbundanweisung stehen, die den `switch`-Text bildet, aber in den Deklarationen enthaltene Initialisierungen werden nicht ausgeführt. Mit der `switch`-Anweisung wird die Steuerung direkt an eine ausführbare Anweisung innerhalb des Texts übertragen. Dabei werden die Zeilen umgangen, die Initialisierungen enthalten.  
  
 In den folgenden Beispielen werden `switch`-Anweisungen veranschaulicht:  
  
```  
switch( c )   
{  
    case 'A':  
        capa++;  
    case 'a':  
        lettera++;  
    default :  
        total++;  
}  
```  
  
 Alle drei Anweisungen des `switch`-Texts in diesem Beispiel werden ausgeführt, wenn `c` gleich `'A'` ist, da vor dem folgenden Fall keine **break**-Anweisung steht. Die Ausführungssteuerung wird auf die erste Anweisung (`capa++;`) übertragen und im verbleibenden Text der Reihe nach fortgeführt. Wenn `c` gleich `'a'` ist, werden `lettera` und `total` erhöht. Nur `total` wird erhöht, wenn `c` ungleich `'A'` oder `'a'` ist.  
  
```  
switch( i )   
{  
    case -1:  
        n++;  
        break;  
    case 0 :  
        z++;  
        break;  
    case 1 :  
        p++;  
        break;  
}  
```  
  
 In diesem Beispiel folgt eine **break**-Anweisung auf jede Anweisung des `switch`-Texts. Die **break**-Anweisung erzwingt eine Beendigung vom Anweisungstext, nachdem eine Anweisung ausgeführt wurde. Wenn `i` gleich -1 ist, wird nur `n` inkrementiert. Die **break**-Anweisung, die auf die `n++;`-Anweisung folgt, führt dazu, dass die Ausführungssteuerung aus dem Anweisungstext übergeben wird und die übrigen Anweisungen übersprungen werden. Wenn `i` gleich 0 ist, wird dementsprechend nur `z` erhöht. Wenn `i` gleich 1 ist, wird nur `p` erhöht. Die abschließende **break**-Anweisung ist nicht unbedingt erforderlich, da die Steuerung am Ende der Verbundanweisung aus dem Text übergeben wird, aus Gründen der Einheitlichkeit ist sie aber enthalten.  
  
 Eine einzelne Anweisung kann mehrere **case**-Bezeichnungen tragen, wie das folgende Beispiel zeigt:  
  
```  
case 'a' :  
case 'b' :  
case 'c' :  
case 'd' :  
case 'e' :  
case 'f' :  hexcvt(c);  
```  
  
 In diesem Beispiel wird im Fall, dass *constant-expression* einem beliebigen Buchstaben zwischen `'a'` und `'f'` entspricht, die `hexcvt`-Funktion aufgerufen.  
  
 **Microsoft-spezifisch**  
  
 In Microsoft C wird die Anzahl von case-Werten in einer `switch`-Anweisung nicht beschränkt. Die Anzahl wird nur durch den verfügbaren Speicher beschränkt. ANSI C erfordert, dass mindestens 257 case-Abschnitte in einer `switch`-Anweisung zulässig sind.  
  
 Bei Microsoft C sind die Microsoft-Erweiterungen standardmäßig aktiviert. Verwenden Sie die /Za-Compileroption, um diese Erweiterungen zu deaktivieren.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [switch-Anweisung (C++)](../cpp/switch-statement-cpp.md)