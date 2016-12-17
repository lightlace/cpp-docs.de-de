---
title: "Verarbeiten der XML-Datei"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "XML-Dokumentation, XML-Datei verarbeiten"
ms.assetid: e70fdeae-80ac-4872-ab24-771c5635cfbf
caps.latest.revision: 15
caps.handback.revision: "15"
ms.author: "mblome"
manager: "ghogen"
---
# Verarbeiten der XML-Datei
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Für jedes Konstrukt, das zum Generieren von Dokumentation gekennzeichnet ist, wird vom Compiler eine ID\-Zeichenfolge generiert.  Weitere Informationen finden Sie unter [Empfohlene Tag\-Dokumentationskommentare](../ide/recommended-tags-for-documentation-comments-visual-cpp.md).  Das Konstrukt wird von der ID\-Zeichenfolge eindeutig identifiziert.  Programme, die die XML\-Datei verarbeiten, können die ID\-Zeichenfolge verwenden, um die entsprechenden .NET Framework\-Metadaten oder das Reflektionselement zu identifizieren, auf die die Dokumentation gilt.  
  
 Die XML\-Datei ist keine hierarchische Darstellung des Codes, es ist eine flache Liste mit einer generierten ID für jedes Element.  
  
 Die folgenden Regeln werden vom Compiler beim Generieren der ID\-Zeichenfolgen beachtet:  
  
-   Die Zeichenfolge darf keine Leerräume enthalten.  
  
-   Der erste Teil der ID\-Zeichenfolge kennzeichnet die Art des zu identifizierenden Members durch ein einzelnes Zeichen, gefolgt von einem Doppelpunkt.  Die folgenden Membertypen werden verwendet:  
  
    |Zeichen|Beschreibung|  
    |-------------|------------------|  
    |N|\-Namespace<br /><br /> Sie können Dokumentationskommentare keinem Namespace hinzufügen, cref Verweise auf einen Namespace möglich.|  
    |T|Typ: Klasse, Schnittstelle, Struktur, Auflistung, Delegat|  
    |D|typedef|  
    |F|Feld|  
    |P|Eigenschaft, einschließlich Indexern oder anderer indizierter Eigenschaften.|  
    |M|Methode \(einschließlich spezieller Methoden wie Konstruktoren, Operatoren usw.\)|  
    |E|Ereignis|  
    |\!|Fehlerzeichenfolge<br /><br /> Der verbleibende Teil der Zeichenfolge enthält Fehlerinformationen.  Der Visual C\+\+\-Compiler generiert Fehlerinformationen für Links, die nicht aufgelöst werden können.|  
  
-   Beim zweiten Teil der Zeichenfolge handelt es sich um den vollqualifizierten Namen eines Elements, beginnend mit dem Namespace\-Stammverzeichnis.  Der Name des Elements, sein einschließender Typen und Typ oder Namespace werden bis zum Punkten getrennt.  Wenn der Name des Elements selbst Punkte enthält, werden sie durch ein Nummernzeichen \(**\#**\) ersetzt.  Es wird davon ausgegangen, dass kein Element HashSIGN direkt in ihrem Namen.  Beispielsweise lautet der vollqualifizierte Name des `String`\-Konstruktors "System.String.\#ctor" sein.  
  
-   Wenn es sich bei Eigenschaften und Methoden um Argumente der Methode handelt, folgt die in Klammern eingeschlossene Argumentliste.  Wenn keine Argumente vorhanden sind, werden keine Klammern verwendet.  Die Argumente werden durch Kommas voneinander getrennt.  Die Codierung jedes Arguments erfolgt genauso wie die Codierung in einer .NET Framework\-Signatur:  
  
    -   Basistypen.  Reguläre Typen, **ELEMENT\_TYPE\_CLASS** oder **ELEMENT\_TYPE\_VALUETYPE**, werden als vollqualifizierter Name des Typs repräsentiert.  
  
    -   Systeminterne Typen, z. B. ELEMENT\_TYPE\_I4, ELEMENT\_TYPE\_OBJECT, ELEMENT\_TYPE\_STRING, ELEMENT\_TYPE\_TYPEDBYREF.  und ELEMENT\_TYPE\_VOID\) werden als der vollqualifizierte Name des entsprechenden Typs des vollständigen, beispielsweise, **System.Int32** oder des **System.TypedReference** dargestellt.  
  
    -   **ELEMENT\_TYPE\_PTR** wird als \*, das auf den geänderten Typ folgt, repräsentiert.  
  
    -   **ELEMENT\_TYPE\_PTR** wird als @, das auf den geänderten Typ folgt, repräsentiert.  
  
    -   **ELEMENT\_TYPE\_PTR** wird als ^, das auf den geänderten Typ folgt, repräsentiert.  Der Visual C\+\+\-Compiler generiert nie dieses.  
  
    -   ELEMENT\_TYPE\_CMOD\_REQ wird als '&#124;' mit nachstehendem vollqualifizierten Namen der Modifiziererklasse repräsentiert, das auf den geänderten Typ folgt.  Der Visual C\+\+\-Compiler generiert nie dieses.  
  
    -   ELEMENT\_TYPE\_CMOD\_OPT wird als '\!' mit nachstehendem vollqualifizierten Namen der Modifiziererklasse repräsentiert, das auf den geänderten Typ folgt.  
  
    -   **ELEMENT\_TYPE\_SZARRAY** wird als \[\], das auf den Elementtyp des Arrays folgt, repräsentiert.  
  
    -   **ELEMENT\_TYPE\_GENERICARRAY** wird als \[?\], das auf den Elementtyp des Arrays folgt, repräsentiert.  Der Visual C\+\+\-Compiler generiert nie dieses.  
  
    -   ELEMENT\_TYPE\_ARRAY wird als \[*lowerbound*:`size`,*lowerbound*:`size`\] repräsentiert, wobei die Anzahl der Kommas durch Rang \- 1 berechnet wird und die untere Grenze sowie die Größe jeder Dimension, sofern bekannt, dezimal repräsentiert werden.  Wenn die untere Grenze oder die Größe nicht angegeben ist, wird sie einfach ausgelassen.  Wenn die untere Grenze und die Größe für eine bestimmte Dimension ausgelassen werden, kann der **:** ebenfalls ausgelassen werden.  \[1:,1:\] ist beispielsweise ein zweidimensionales Array mit 1 als unterer Grenze und nicht angegebenen Größen.  
  
    -   ELEMENT\_TYPE\_FNPTR wird als "\=FUNC:`type`\(*signature*\)" repräsentiert, wobei `type` den Rückgabetyp darstellt und es sich bei *signature* um die Argumente der Methode handelt.  Sind keine Argumente vorhanden, werden keine Klammern verwendet.  Der Visual C\+\+\-Compiler generiert nie dieses.  
  
     Die folgenden Signaturkomponenten werden nicht repräsentiert, weil sie nicht zur Unterscheidung überladener Methoden verwendet werden:  
  
    -   Aufrufkonvention  
  
    -   Rückgabetyp  
  
    -   ELEMENT\_TYPE\_SENTINEL  
  
-   Nur Konvertierungsoperatoren, der Rückgabewert der Methode wird als codiert "&#124;" gefolgt vom Rückgabetyp, wie zuvor codiert.  
  
-   Bei generischen Typen folgt auf den Namen des Typs ein Graviszeichen und dann eine Zahl, die die Anzahl der generischen Typparameter angibt.  Beispiel:  
  
    ```  
    <member name="T:MyClass`2">  
    ```  
  
     Für einen Typ, der als `public class MyClass<T, U>` definiert ist.  
  
     Bei Methoden, die generische Typen als Parameter verwenden, werden die generischen Parameter des Typs als Zahlen mit vorangestelltem Graviszeichen angegeben \(z. B. \`0,\`1\).  Jede Zahl stellt eine bei 0 beginnende Arraynotation für die generischen Parameter des Typs dar.  
  
## Beispiel  
 Die folgenden Beispiele zeigen, wie die ID\-Zeichenfolgen für eine Klasse und ihre Member generiert werden.  
  
```  
// xml_id_strings.cpp  
// compile with: /clr /doc /LD  
///   
namespace N {    
// "N:N"  
  
   /// <see cref="System" />  
   //  <see cref="N:System"/>  
   ref class X {      
   // "T:N.X"  
  
   protected:  
      ///   
      !X(){}     
      // "M:N.X.Finalize", destructor's representation in metadata  
  
   public:  
      ///   
      X() {}     
      // "M:N.X.#ctor"  
  
      ///   
      static X() {}     
      // "M:N.X.#cctor"  
  
      ///   
      X(int i) {}     
      // "M:N.X.#ctor(System.Int32)"  
  
      ///   
      ~X() {}     
      // "M:N.X.Dispose", Dispose function representation in metadata  
  
      ///   
      System::String^ q;     
      // "F:N.X.q"  
  
      ///   
      double PI;     
      // "F:N.X.PI"  
  
      ///   
      int f() { return 1; }     
      // "M:N.X.f"  
  
      ///   
      int bb(System::String ^ s, int % y, void * z) { return 1; }  
      // "M:N.X.bb(System.String,System.Int32@,System.Void*)"  
  
      ///   
      int gg(array<short> ^ array1, array< int, 2 >^ IntArray) { return 0; }   
      // "M:N.X.gg(System.Int16[], System.Int32[0:,0:])"  
  
      ///   
      static X^ operator+(X^ x, X^ xx) { return x; }  
     // "M:N.X.op_Addition(N.X,N.X)"  
  
      ///   
      property int prop;     
      // "M:N.X.prop"  
  
      ///   
      property int prop2 {     
      // "P:N.X.prop2"  
  
         ///   
         int get() { return 0; }  
         // M:N.X.get_prop2  
  
         ///   
         void set(int i) {}  
         // M:N.X.set_prop2(System.Int32)  
      }  
  
      ///   
      delegate void D(int i);   
      // "T:N.X.D"  
  
      ///   
      event D ^ d;   
      // "E:N.X.d"  
  
      ///   
      ref class Nested {};   
      // "T:N.X.Nested"  
  
      ///   
      static explicit operator System::Int32 (X x) { return 1; }   
      // "M:N.X.op_Explicit(N.X!System.Runtime.CompilerServices.IsByValue)~System.Int32"  
   };  
}  
```  
  
## Siehe auch  
 [XML\-Dokumentation](../ide/xml-documentation-visual-cpp.md)