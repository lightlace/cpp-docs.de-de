---
title: "scanf-Breitenangabe"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apilocation: 
  - "msvcr100.dll"
  - "msvcr120.dll"
  - "msvcr80.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr90.dll"
apitype: "DLLExport"
f1_keywords: 
  - "scanf"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "scanf-Funktion, Breitenspezifikation"
ms.assetid: 94b4e8fe-c4a2-4799-8b6c-a2cf28ffb09c
caps.latest.revision: 16
caps.handback.revision: "16"
ms.author: "corob"
manager: "ghogen"
---
# scanf-Breitenangabe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Diese Informationen gelten für die Interpretation von Formatzeichenfolgen in der `scanf`\-Funktionsreihe, einschließlich der sicheren Versionen wie `scanf_s`.  Diese Funktionen nehmen in der Regel an, dass der Eingabestream in eine Folge von Token unterteilt ist.  Token werden durch Leerzeichen \(Leerzeichen, Tabstoppzeichen oder Zeilenumbruch\) oder im Fall von numerischen Typen durch das natürliche Ende dieser getrennt, das durch das erste nicht in numerischen Text konvertierbare Zeichen angegeben ist.  Mit den Breitenangaben können Sie jedoch festlegen, dass die Analyse der Eingabe vor dem natürlichen Ende eines Tokens beendet wird.  
  
 Die *Breiten*angabe besteht aus Zeichen zwischen `%` und dem Typfeldspezifizierer. Sie umfasst u. a. eine positive ganze Zahl, Feld *Breite* genannt, und die die Größe des Felds angebenden Zeichen, die ggf. auch als Modifizierer des Feldtyps betrachtet werden können, z. B. die Angabe, ob der Ganzzahltyp **kurz**oder**lang** ist.  Solche Zeichen werden als das Größenpräfix bezeichnet.  
  
## Das Feld „Breite“  
 Das Feld *Breite*Feld ist eine positive ganze Dezimalzahl, die die maximale Anzahl der für dieses Feld zu lesenden Zeichen steuert.  Es werden nicht mehr als die angegebenen *Breiten*zeichen konvertiert und im entsprechenden `argument` gespeichert.  Weniger als die angegebenen *Breiten*zeichen werden möglicherweise gelesen, wenn ein nicht zu konvertierendes Leerzeichen \(Leerzeichen, Tabstoppzeichen oder Zeilenumbruch\) oder Zeichen auftritt, bevor das Ende von *Breite*erreicht ist.  
  
 Die Breitenangabe ist unabhängig und unterscheidet sich vom Puffergrößenargument, das von den sicheren Versionen dieser Funktionen erfordert wird \(z. B. `scanf_s``wscanf_s` usw.\).  Im folgenden Beispiel beträgt die Breitenangabe 20 und gibt somit an, dass bis zu 20 Zeichen aus dem Eingabestream gelesen werden.  Die Pufferlänge beträgt 21 und schließt somit die möglichen 20 Zeichen mit dem Null\-Abschlusszeichen ein:  
  
```  
char str[21];  
scanf_s("%20s", str, 21);  
```  
  
 Wenn das Feld *Breite* nicht verwendet wird, versucht `scanf_s` das gesamte Token in der Zeichenfolge zu lesen.  Wenn die angegebene Größe nicht für das gesamte Token ausreicht, wird nichts in die Zielzeichenfolge geschrieben.  Wenn das Feld *Breite* angegeben ist, werden die ersten *Breite*zeichen im Token in die Zielzeichenfolge zusammen mit dem Null\-Abschlusszeichen geschrieben.  
  
## Das Größenpräfix  
 Die optionalen Präfixe **h**, **l**, **ll**, **I64** und**L** geben die Größe des `argument`an \(lang oder kurz, Einzelbytezeichen oder Breitzeichen, je nach Typzeichen, die sie ändern\).  Diese Formatangabezeichen werden in `scanf`\- oder `wscanf`\-Funktionen mit Typzeichen für die Interpretation von Argumenten verwendet, wie in der folgenden Tabelle dargestellt.  Das Typpräfix **I64** ist eine Microsoft\-Erweiterung und ist nicht ANSI\-kompatibel.  Typzeichen und ihre Bedeutungen werden in der Tabelle „Typzeichen für scanf\-Funktionen“ unter [scanf\-Typenfeldzeichen](../c-runtime-library/scanf-type-field-characters.md) erläutert.  
  
> [!NOTE]
>  Die **h**\-, **l**\- und **L**\-Präfixe stellen beim Verwenden mit Daten vom Typ `char` Microsoft\-Erweiterungen dar.  
  
### Größenpräfixe für die Formattypspezifizierer scanf und wscanf  
  
|Angabe von|Präfix|Mit Typspezifizierer|  
|----------------|------------|--------------------------|  
|**double**|**c**|**e**, **E**, **f**, **g** oder **G**|  
|**long double** \(identisch mit double\)|**L**|**e**, **E**, **f**, **g** oder **G**|  
|**long int**|**c**|**d**, **i**, **o**, **x** oder **X**|  
|**long unsigned int**|**c**|**n**|  
|**long long**|**ll**|**d**, **i**, **o**, **x** oder **X**|  
|`short int`|**h**|**d**, **i**, **o**, **x** oder **X**|  
|**short unsigned int**|**h**|**n**|  
|\_\_**int64**|**I64**|**d**, **i**, **o**, **u**, **x** oder **X**|  
|Einzelbytezeichen mit `scanf`|**h**|**c** oder **C**|  
|Einzelbytezeichen mit `wscanf`|**h**|**c** oder **C**|  
|Breitzeichen mit `scanf`|**c**|**c** oder **C**|  
|Breitzeichen mit `wscanf`|**c**|**c** oder **C**|  
|Einzelbytezeichenfolge mit `scanf`|**h**|**s** oder **S**|  
|Einzelbytezeichenfolge mit `wscanf`|**h**|**s** oder **S**|  
|Breitzeichenfolge mit `scanf`|**c**|**s** oder **S**|  
|Breitzeichenfolge mit `wscanf`|**c**|**s** oder **S**|  
  
 Die folgenden Beispiele verwenden die **h**\- und **l**\-Präfixe mit den `scanf_s`\-Funktionen und `wscanf_s`\-Funktionen:  
  
```  
scanf_s("%ls", &x, 2);     // Read a wide-character string  
wscanf_s(L"%hC", &x, 2);    // Read a single-byte character  
```  
  
 Lassen Sie beim Verwenden einer nicht sicheren Funktion in der `scanf`\-Reihe den Größenparameter aus, der die Pufferlänge des vorherigen Arguments angibt.  
  
## Lesen von nicht durch Trennzeichen getrennten Zeichenfolgen  
 Zum Lesen von Zeichenfolgen, die nicht durch Trennzeichen getrennt sind, kann ein Zeichensatz in Klammern \(**\[\]**\) für das **s**\(Zeichenfolgen\)\-Typzeichen ersetzt werden.  Der Zeichensatz in Klammern wird als Steuerzeichenfolge bezeichnet.  Das entsprechende Eingabefeld wird bis zum ersten Zeichen gelesen, das nicht in der Steuerzeichenfolge enthalten ist.  Wenn das erste Zeichen im Satz ein Caretzeichen \(**^**\) ist, wird die Auswirkung umgekehrt: das Eingabefeld wird bis zum ersten Zeichen gelesen, das im übrigen Zeichensatz enthalten ist.  
  
 Beachten Sie, dass **%\[a\-z\]** und **%\[z\-a\]** auf die gleiche Weise wie **%\[abcde...z\]** interpretiert werden.  Dies ist eine häufige `scanf`\-Funktionserweiterung, beachten Sie jedoch, dass sie nicht vom ANSI\-Standard erfordert wird  
  
## Lesen von nicht beendeten Zeichenfolgen  
 Verwenden Sie zum Speichern einer Zeichenfolge ohne ein Null\-Abschlusszeichen \(„\\0“\) die Spezifikation `%`*n***c**, wobei *n* eine ganze Dezimalzahl ist.  In diesem Fall gibt das **c**\-Typzeichen an, dass das Argument ein Zeiger auf ein Zeichenarray ist.  Die nächsten *n*\-Zeichen werden aus dem Eingabestream in die angegebene Position gelesen und es wird kein Nullzeichen \(„\\0“\) angefügt.  Wenn *n* nicht angegeben ist, lautet der Standardwert 1.  
  
## Wenn scanf das Lesen eines Felds beendet  
 Die `scanf`\-Funktion überprüft Zeichen für Zeichen jedes Eingabefeld.  Aus den folgenden Gründen beendet sie möglicherweise das Lesen eines bestimmten Eingabefelds, bevor ein Leerzeichen auftritt:  
  
-   Die angegebene Breite wurde erreicht.  
  
-   Das nächste Zeichen kann nicht wie angegeben konvertiert werden.  
  
-   Das nächste Zeichen weist Konflikte mit einem Zeichen in der Steuerzeichenfolge auf, mit dem es übereinstimmen soll.  
  
-   Das nächste Zeichen kann nicht in einem angegebenen Zeichensatz angezeigt werden.  
  
 Wenn die `scanf`\-Funktion, unabhängig von dem Grund, das Lesen eines Eingabefelds beendet, beginnt das nächste Eingabefeld beim ersten ungelesenen Zeichen.  Das einen Konflikt aufweisende Zeichen, falls vorhanden, gilt als ungelesen und stellt das erste Zeichen des nächsten Eingabefelds oder das erste Zeichen in nachfolgenden Lesevorgängen des Eingabestreams dar.  
  
## Siehe auch  
 [scanf, \_scanf\_l, wscanf, \_wscanf\_l](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [scanf\_s, \_scanf\_s\_l, wscanf\_s, \_wscanf\_s\_l](../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)   
 [Formatangabefelder: scanf\- und wscanf\-Funktionen](../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md)   
 [scanf\-Typenfeldzeichen](../c-runtime-library/scanf-type-field-characters.md)