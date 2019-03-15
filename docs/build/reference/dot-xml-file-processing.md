---
title: Verarbeiten der XML-Datei
ms.date: 11/04/2016
helpviewer_keywords:
- XML documentation, processing XML file
ms.assetid: e70fdeae-80ac-4872-ab24-771c5635cfbf
ms.openlocfilehash: 1a0d231a066209307041681232cc3410210d4d02
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57825312"
---
# <a name="xml-file-processing"></a>Verarbeiten der XML-Datei

Für jedes Konstrukt, das zum Generieren von Dokumentation gekennzeichnet ist, wird vom Compiler eine ID-Zeichenfolge generiert. Weitere Informationen finden Sie unter [Recommended Tags Documentation Comments (Empfohlene Tags für Dokumentationskommentare)](recommended-tags-for-documentation-comments-visual-cpp.md). Das Konstrukt wird über die ID-Zeichenfolge eindeutig identifiziert. Programme, die die XML-Datei verarbeiten, können mithilfe der ID-Zeichenfolge das entsprechende .NET Framework-Metadaten- oder Reflektionselement identifizieren, für das die Dokumentation gilt.

Die XML-Datei enthält keine hierarchische Darstellung des Codes. Es handelt sich um eine flache Liste mit einer generierten ID für jedes Element.

Der Compiler beachtet beim Generieren der ID-Zeichenfolgen die folgenden Regeln:

- In der Zeichenfolge wird kein Leerraum platziert.

- Der erste Teil der ID-Zeichenfolge kennzeichnet die Art des zu identifizierenden Members durch ein einzelnes Zeichen, gefolgt von einem Doppelpunkt. Die folgenden Membertypen werden verwendet:

  | Zeichen | Beschreibung |
  |---------------|-----------------|
  | N | namespace<br /><br /> Einem Namespace können keine Dokumentationskommentare hinzugefügt werden. Allerdings sind cref-Verweise auf einen Namespace möglich. |
  | T | Typ: Klasse, Schnittstelle, Struktur, Enumeration, Delegat |
  | D | Typedef |
  | F | Feld |
  | P | Eigenschaft (einschließlich von Indexern oder anderen indizierten Eigenschaften) |
  | M | Methode (einschließlich spezieller Methoden wie Konstruktoren, Operatoren usw.) |
  | E | event |
  | ! | Fehlerzeichenfolge<br /><br /> Der verbleibende Teil der Zeichenfolge enthält Fehlerinformationen. Der MSVC-Compiler generiert die Fehlerinformationen für Links, die nicht aufgelöst werden kann. |

- Beim zweiten Teil der Zeichenfolge handelt es sich um den vollqualifizierten Namen eines Elements, beginnend mit dem Namespace-Stammverzeichnis. Der Name des Elements, die einschließenden Typen und der Namespace sind durch Punkte getrennt. Wenn der Name des Elements selbst Punkte enthält, werden sie durch ein Rautezeichen (#) ersetzt. Es wird vorausgesetzt, dass kein Element direkt im Namen ein Rautezeichen enthält. Der vollqualifizierte Name des `String`-Konstruktors würde beispielsweise „System.String.#ctor“ lauten.

- Wenn es sich bei Eigenschaften und Methoden um Argumente der Methode handelt, folgt die in Klammern eingeschlossene Argumentliste. Wenn keine Argumente vorhanden sind, werden keine Klammern verwendet. Die Argumente werden durch Kommas voneinander getrennt. Die Codierung jedes Arguments erfolgt genauso wie die Codierung in einer .NET Framework-Signatur:

  - Basistypen. Reguläre Typen (ELEMENT_TYPE_CLASS oder ELEMENT_TYPE_VALUETYPE) werden als vollqualifizierter Name des Typs dargestellt.

  - Systeminterne Typen (z.B. ELEMENT_TYPE_I4, ELEMENT_TYPE_OBJECT, ELEMENT_TYPE_STRING, ELEMENT_TYPE_TYPEDBYREF und ELEMENT_TYPE_VOID) werden als vollqualifizierter Name des entsprechenden vollständigen Typs dargestellt, z.B. **System.Int32** oder **System.TypedReference**.

  - ELEMENT_TYPE_PTR wird als * dargestellt, das auf den geänderten Typ folgt.

  - ELEMENT_TYPE_BYREF wird als \@ dargestellt, das auf den geänderten Typ folgt.

  - ELEMENT_TYPE_PINNED wird als ^ dargestellt, das auf den geänderten Typ folgt. Der MSVC-Compiler wird die dies niemals generiert.

  - ELEMENT_TYPE_CMOD_REQ wird als &#124; und vollqualifizierter Name der Modifiziererklasse dargestellt, das bzw. der auf den geänderten Typ folgt. Der MSVC-Compiler wird die dies niemals generiert.

  - ELEMENT_TYPE_CMOD_OPT wird als ! mit nachstehendem vollqualifizierten Namen der Modifiziererklasse dargestellt, das auf den geänderten Typ folgt.

  - ELEMENT_TYPE_SZARRAY wird als [] dargestellt, das auf den Elementtyp des Arrays folgt.

  - ELEMENT_TYPE_GENERICARRAY wird als [?] dargestellt, das auf den Elementtyp des Arrays folgt. Der MSVC-Compiler wird die dies niemals generiert.

  - ELEMENT_TYPE_ARRAY wird als [*lowerbound*:`size`,*lowerbound*:`size`] dargestellt, wobei die Anzahl von Kommas als Rang minus 1 berechnet wird und die untere Grenze sowie die Größe jeder Dimension – sofern bekannt – dezimal dargestellt werden. Wenn die untere Grenze oder die Größe nicht angegeben ist, wird sie einfach ausgelassen. Wenn die untere Grenze und die Größe für eine bestimmte Dimension ausgelassen werden, kann der Doppelpunkt (:) ebenfalls ausgelassen werden. [1:,1:] ist beispielsweise ein zweidimensionales Array mit 1 als unterer Grenze und nicht angegebenen Größen.

  - ELEMENT_TYPE_FNPTR wird als „=FUNC:`type`(*signature*)“ dargestellt, wobei `type` den Rückgabetyp angibt und es sich bei *signature* um die Argumente der Methode handelt. Sind keine Argumente vorhanden, werden keine Klammern verwendet. Der MSVC-Compiler wird die dies niemals generiert.

  Die folgenden Signaturkomponenten werden nicht dargestellt, weil sie nicht zur Unterscheidung überladener Methoden verwendet werden:

  - Aufrufkonvention

  - Rückgabetyp

  - ELEMENT_TYPE_SENTINEL

- Nur für Konvertierungsoperatoren wird wie zuvor gezeigt der Rückgabewert der Methode als „~“ gefolgt vom Rückgabewert codiert.

- Bei generischen Typen folgt auf den Namen des Typs ein Graviszeichen und dann eine Zahl, mit der die Anzahl generischer Typparameter angegeben wird.  Ein auf ein Objekt angewendeter

    ```xml
    <member name="T:MyClass`2">
    ```

  Für einen Typ, der als `public class MyClass<T, U>` definiert ist.

  Bei Methoden, die generische Typen als Parameter verwenden, werden die generischen Parameter des Typs als Zahlen mit vorangestelltem Graviszeichen angegeben (z.B. \`0, \`1).  Jede Zahl stellt eine bei 0 beginnende Arraynotation für die generischen Parameter des Typs dar.

## <a name="example"></a>Beispiel

In den folgenden Beispielen wird veranschaulicht, wie die ID-Zeichenfolgen für eine Klasse und ihre Member generiert werden würden.

```cpp
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

## <a name="see-also"></a>Siehe auch

[XML-Dokumentation](xml-documentation-visual-cpp.md)
