---
layout: oldGuidelines
---
<div xmlns="http://www.w3.org/1999/xhtml">
   <article class="page type-page status-publish hentry">
      <div class="entry-content">
         <div class="panel-grid">
            <div class="panel-grid-cell" style="width: 65%; float: left;">
               <div class="panel widget widget_text panel-first-child panel-last-child">
                  <div class="textwidget">
                     <section class="div1" id="analysis">
                        <header>
                           <h1><span class="headingNumber">7 </span><span class="head">Analytical
                                 Information</span></h1>
                        </header>
                        <p>This chapter describes the use of attributes that
                           capture data which may be useful for analytical purposes. The analysis module provides
                           attributes that record relationships between entities found in the encoding. These
                           attributes may be used differently by different users, depending on the purpose of
                           the
                           analysis. These Guidelines recommend that encoders employ commonly accepted analytical
                           practices, such as "functional analysis" or "Schenkerian analysis", and document their
                           use
                           in the <a class="link_odd_elementSpec" href="/documentation/2.1.1/encodingDesc">encodingDesc</a> described in section <a class="link_ptr" href="/documentation/2.1.1/header#encodingDescription" title="Encoding Description"><span class="headingNumber">2.2 </span>Encoding Description</a>. For general information on
                           musical analysis, please consult Grove Music Online, "<a class="link_ref" href="http://www.oxfordmusiconline.com/subscriber/article/grove/music/41862pg1#S41862.1">Analysis</a>".
                        </p>
                        <div class="div2" id="analysisDescribingRelationships">
                           <h2><span class="headingNumber">7.1 </span><span class="head">General Relationships Between
                                 Elements</span></h2>
                           <p>The relationships between event elements, such as note, chord,
                              and rest, are the basic material of musical analysis; the attributes described below
                              ensure a closed network of these relations and provide the opportunity to record data
                              useful for common analytical tasks. In the context of a formal analysis, for instance,
                              the attributes presented here can be useful in the capture information about the
                              structure of a musical work.
                           </p>
                           <p>The analysis module offers several attributes in the
                              <a class="link_odd" href="/documentation/2.1.1/att.common.anl">att.common.anl</a> class for the
                              description of basic relationships:
                           </p>
                           <ul class="specList">
                              
                              <li><span class="specList-classSpec"><a href="/documentation/2.1.1/att.common.anl">att.common.anl</a></span>
                                 Common analytical attributes. When the meiLinkAlign module is used, the when attribute
                                 is also a member of this attribute class.
                                 <table class="specDesc">
                                    
                                    <tr>
                                       
                                       <td class="Attribute"><span class="att">copyof</span></td>
                                       
                                       <td>points to an element of which the current element is a copy.</td>
                                       
                                    </tr>
                                    
                                    <tr>
                                       
                                       <td class="Attribute"><span class="att">corresp</span></td>
                                       
                                       <td>used to point to other elements that correspond to this one in a generic
                                          fashion.
                                       </td>
                                       
                                    </tr>
                                    
                                    <tr>
                                       
                                       <td class="Attribute"><span class="att">next</span></td>
                                       
                                       <td>used to point to the next event(s) in a user-defined collection.</td>
                                       
                                    </tr>
                                    
                                    <tr>
                                       
                                       <td class="Attribute"><span class="att">prev</span></td>
                                       
                                       <td>points to the previous event(s) in a user-defined collection.</td>
                                       
                                    </tr>
                                    
                                    <tr>
                                       
                                       <td class="Attribute"><span class="att">sameas</span></td>
                                       
                                       <td>points to an element that is the same as the current element but is not a
                                          literal copy of the current element.
                                       </td>
                                       
                                    </tr>
                                    
                                    <tr>
                                       
                                       <td class="Attribute"><span class="att">synch</span></td>
                                       
                                       <td>points to elements that are synchronous with the current element.</td>
                                       
                                    </tr>
                                    
                                 </table>
                              </li>
                              
                              <li><span class="specList-classSpec"><a href="/documentation/2.1.1/att.alignment">att.alignment</a></span>
                                 Temporal alignment attributes.
                                 <table class="specDesc">
                                    
                                    <tr>
                                       
                                       <td class="Attribute"><span class="att">when</span></td>
                                       
                                       <td>indicates the point of occurrence of this feature along a time line. Its value
                                          must be the ID of a &lt;when&gt; element elsewhere in the document.
                                       </td>
                                       
                                    </tr>
                                    
                                 </table>
                              </li>
                              
                           </ul>
                           <p>These attributes accommodate the encoding of linkages between the element carrying
                              the attribute and one or more other elements. All of them use URIs to establish the
                              connection. While the examples below illustrate relationships between musical events,
                              their use is not restricted to musical events. On the contrary, these attributes can
                              be
                              used to capture information about relations between any elements.
                           </p>
                           <p>Using these
                              attributes makes it possible to create relationships between events, which are often
                              widely-spaced in both encoded order and time. The attributes allow a large number
                              of
                              connections, enhancing the informational content, and therefore the potential
                              usefulness, of the encoding.
                           </p>
                           <p>The <span class="att">copyof</span> attribute points
                              to an element of which the current element is a copy. It can be used to repeat a note,
                              for example, without encoding the whole <a class="link_odd_elementSpec" href="/documentation/2.1.1/note">note</a> element
                              again. The copy is a ‘deep’one; that is, the <span class="att">copyof</span> attribute
                              copies all attributes and child elements which belong to the copied element, such
                              as the
                              <span class="att">dur</span> and <span class="att">oct</span> attributes of a copied
                              <a class="link_odd_elementSpec" href="/documentation/2.1.1/note">note</a>. The value of the <span class="att">copyof</span>
                              attribute must be a URI, which usually refers to an element in the current document.
                              The
                              following example demonstrates use of the <span class="att">copyof</span>
                              attribute:
                           </p>
                           <div id="index.xml-egXML-d39e9863" class="pre egXML_valid">
                              <span data-indentation="1" class="element">&lt;measure <span class="attribute">n</span>="<span class="attributevalue">1</span>"&gt;</span><br />   <span data-indentation="2" class="element">&lt;staff <span class="attribute">n</span>="<span class="attributevalue">1</span>"&gt;</span><br />
                                  <span data-indentation="3" class="element">&lt;layer&gt;</span><br />       <span data-indentation="4" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">4</span>" <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">g</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">analysis.note1_1</span>"/&gt;</span><br />     <span data-indentation="3" class="element">&lt;/layer&gt;</span><br />   <span data-indentation="2" class="element">&lt;/staff&gt;</span><br />
                              <span data-indentation="1" class="element">&lt;/measure&gt;</span><br />
                              <span data-indentation="1" class="element">&lt;measure <span class="attribute">n</span>="<span class="attributevalue">2</span>"&gt;</span><br />   <span data-indentation="2" class="element">&lt;staff <span class="attribute">n</span>="<span class="attributevalue">1</span>"&gt;</span><br />
                                  <span data-indentation="3" class="element">&lt;layer&gt;</span><br />       <span data-indentation="4" class="element">&lt;note <span class="attribute">copyof</span>="<span class="attributevalue">#analysis.note1_1</span>"/&gt;</span><br />     <span data-indentation="3" class="element">&lt;/layer&gt;</span><br />   <span data-indentation="2" class="element">&lt;/staff&gt;</span><br />
                              <span data-indentation="1" class="element">&lt;/measure&gt;</span>     
                           </div>
                           <p>In this example. the <a class="link_odd_elementSpec" href="/documentation/2.1.1/note">note</a> in the second measure has exactly the same
                              characteristics as the <a class="link_odd_elementSpec" href="/documentation/2.1.1/note">note</a> in the first <a class="link_odd_elementSpec" href="/documentation/2.1.1/measure">measure</a>.
                           </p>
                           <p>Using <span class="att">copyof</span> is not
                              limited to copying events. The <span class="att">copyof</span> attribute can also be
                              used to copy an entire <a class="link_odd_elementSpec" href="/documentation/2.1.1/measure">measure</a> or <a class="link_odd_elementSpec" href="/documentation/2.1.1/staff">staff</a>. When there are many repeated features, the use of the <span class="att">copyof</span> greatly reduces encoding effort. The image and the following
                              encoding of the beginning of Schubert's <span class="titlem">Erlkönig</span> illustrates
                              the benefit of using the <span class="att">copyof</span> attribute.
                           </p>
                           <figure class="figure">
                              <figcaption class="caption">Figure 21. First measure of Schubert's
                                 Erlkönig
                              </figcaption><img src="./Images/modules/analysis/Schubert_Erlkonig_Op1_m1.png" alt="First measure of Schubert's Erlkönig" class="graphic" ></figure>
                           <div id="index.xml-egXML-d39e9927" class="pre egXML_valid">
                              <span data-indentation="1" class="element">&lt;measure&gt;</span><br />   <span data-indentation="2" class="element">&lt;staff <span class="attribute">n</span>="<span class="attributevalue">1</span>"&gt;</span><br />
                                  <span data-indentation="3" class="element">&lt;layer&gt;</span><br />       <span data-indentation="4" class="element">&lt;mRest/&gt;</span><br />     <span data-indentation="3" class="element">&lt;/layer&gt;</span><br />   <span data-indentation="2" class="element">&lt;/staff&gt;</span><br />   <span data-indentation="2" class="element">&lt;staff <span class="attribute">n</span>="<span class="attributevalue">2</span>"&gt;</span><br />
                                  <span data-indentation="3" class="element">&lt;layer&gt;</span><br />       <span data-indentation="4" class="element">&lt;tuplet <span class="attribute">num</span>="<span class="attributevalue">3</span>" <span class="attribute">num.visible</span>="<span class="attributevalue">true</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">analysis.tup1</span>"&gt;</span><br />         <span data-indentation="5" class="element">&lt;chord <span class="attribute">dur</span>="<span class="attributevalue">8</span>"&gt;</span><br />           <span data-indentation="6" class="element">&lt;note <span class="attribute">oct</span>="<span class="attributevalue">3</span>" <span class="attribute">pname</span>="<span class="attributevalue">g</span>"/&gt;</span><br />           <span data-indentation="6" class="element">&lt;note <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">g</span>"/&gt;</span><br />
                                      <span data-indentation="5" class="element">&lt;/chord&gt;</span><br />         <span data-indentation="5" class="element">&lt;chord <span class="attribute">dur</span>="<span class="attributevalue">8</span>"&gt;</span><br />           <span data-indentation="6" class="element">&lt;note <span class="attribute">oct</span>="<span class="attributevalue">3</span>" <span class="attribute">pname</span>="<span class="attributevalue">g</span>"/&gt;</span><br />           <span data-indentation="6" class="element">&lt;note <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">g</span>"/&gt;</span><br />         <span data-indentation="5" class="element">&lt;/chord&gt;</span><br />         <span data-indentation="5" class="element">&lt;chord <span class="attribute">dur</span>="<span class="attributevalue">8</span>"&gt;</span><br />           <span data-indentation="6" class="element">&lt;note <span class="attribute">oct</span>="<span class="attributevalue">3</span>" <span class="attribute">pname</span>="<span class="attributevalue">g</span>"/&gt;</span><br />           <span data-indentation="6" class="element">&lt;note <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">g</span>"/&gt;</span><br />         <span data-indentation="5" class="element">&lt;/chord&gt;</span><br />
                                    <span data-indentation="4" class="element">&lt;/tuplet&gt;</span><br />       <span data-indentation="4" class="element">&lt;tuplet <span class="attribute">copyof</span>="<span class="attributevalue">#analysis.tup1</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">analysis.tup2</span>"/&gt;</span><br />       <span data-indentation="4" class="element">&lt;tuplet <span class="attribute">copyof</span>="<span class="attributevalue">#analysis.tup1</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">analysis.tup3</span>"/&gt;</span><br />       <span data-indentation="4" class="element">&lt;tuplet <span class="attribute">copyof</span>="<span class="attributevalue">#analysis.tup1</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">analysis.tup4</span>"/&gt;</span><br />     <span data-indentation="3" class="element">&lt;/layer&gt;</span><br />   <span data-indentation="2" class="element">&lt;/staff&gt;</span><br />   <span data-indentation="2" class="element">&lt;staff <span class="attribute">n</span>="<span class="attributevalue">3</span>"&gt;</span><br />     <span data-indentation="3" class="element">&lt;layer&gt;</span><br />       <span data-indentation="4" class="element">&lt;mRest/&gt;</span><br />     <span data-indentation="3" class="element">&lt;/layer&gt;</span><br />   <span data-indentation="2" class="element">&lt;/staff&gt;</span><br />
                              <span data-indentation="1" class="element">&lt;/measure&gt;</span>     
                           </div>
                           <p>This example can be reduced
                              further by using <span class="att">copyof</span> inside the initial tuplet to represent
                              the repeated chords:
                           </p>
                           <div id="index.xml-egXML-d39e9989" class="pre egXML_valid">
                              <span data-indentation="1" class="element">&lt;measure&gt;</span><br />   <span data-indentation="2" class="element">&lt;staff <span class="attribute">n</span>="<span class="attributevalue">1</span>"&gt;</span><br />
                                  <span data-indentation="3" class="element">&lt;layer&gt;</span><br />       <span data-indentation="4" class="element">&lt;mRest/&gt;</span><br />     <span data-indentation="3" class="element">&lt;/layer&gt;</span><br />   <span data-indentation="2" class="element">&lt;/staff&gt;</span><br />   <span data-indentation="2" class="element">&lt;staff <span class="attribute">n</span>="<span class="attributevalue">2</span>"&gt;</span><br />
                                  <span data-indentation="3" class="element">&lt;layer&gt;</span><br />       <span data-indentation="4" class="element">&lt;tuplet <span class="attribute">num</span>="<span class="attributevalue">3</span>" <span class="attribute">num.visible</span>="<span class="attributevalue">true</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">analysis.tup5</span>"&gt;</span><br />         <span data-indentation="5" class="element">&lt;chord <span class="attribute">dur</span>="<span class="attributevalue">8</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">analysis.t1c1</span>"&gt;</span><br />           <span data-indentation="6" class="element">&lt;note <span class="attribute">oct</span>="<span class="attributevalue">3</span>" <span class="attribute">pname</span>="<span class="attributevalue">g</span>"/&gt;</span><br />           <span data-indentation="6" class="element">&lt;note <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">g</span>"/&gt;</span><br />         <span data-indentation="5" class="element">&lt;/chord&gt;</span><br />
                                      <span data-indentation="5" class="element">&lt;chord <span class="attribute">copyof</span>="<span class="attributevalue">#analysis.t1c1</span>"/&gt;</span><br />         <span data-indentation="5" class="element">&lt;chord <span class="attribute">copyof</span>="<span class="attributevalue">#analysis.t1c1</span>"/&gt;</span><br />       <span data-indentation="4" class="element">&lt;/tuplet&gt;</span><br />       <span data-indentation="4" class="element">&lt;tuplet <span class="attribute">copyof</span>="<span class="attributevalue">#analysis.tup5</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">analysis.tup6</span>"/&gt;</span><br />       <span data-indentation="4" class="element">&lt;tuplet <span class="attribute">copyof</span>="<span class="attributevalue">#analysis.tup5</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">analysis.tup7</span>"/&gt;</span><br />       <span data-indentation="4" class="element">&lt;tuplet <span class="attribute">copyof</span>="<span class="attributevalue">#analysis.tup5</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">analysis.tup8</span>"/&gt;</span><br />     <span data-indentation="3" class="element">&lt;/layer&gt;</span><br />   <span data-indentation="2" class="element">&lt;/staff&gt;</span><br />   <span data-indentation="2" class="element">&lt;staff <span class="attribute">n</span>="<span class="attributevalue">3</span>"&gt;</span><br />     <span data-indentation="3" class="element">&lt;layer&gt;</span><br />       <span data-indentation="4" class="element">&lt;mRest/&gt;</span><br />     <span data-indentation="3" class="element">&lt;/layer&gt;</span><br />   <span data-indentation="2" class="element">&lt;/staff&gt;</span><br />
                              <span data-indentation="1" class="element">&lt;/measure&gt;</span>     
                           </div>
                           <p>While <span class="att">copyof</span> signifies a duplicate copy of an element, the <span class="att">sameas</span> indicates that the current element represents exactly the same entity
                              as the one referenced in <span class="att">sameas</span>. Use of <span class="att">sameas</span> is used for describing the same entity from multiple perspectives,
                              e.g., the same event in two layers. The following example illustrates the sharing
                              of one
                              note head between two voices in the first full measure of a chorale:
                           </p>
                           <figure class="figure">
                              <figcaption class="caption">Figure 22. Bach Chorale, <span class="titlem">Ach Gott, vom Himmel sieh' darein</span>, m. 1-2
                              </figcaption><img src="./Images/modules/analysis/chor003_m1-2.png" alt="Bach Chorale, , m. 1-2" class="graphic" style=" height:200px;" ></figure>
                           <div id="index.xml-egXML-d39e10057" class="pre egXML_valid">
                              <span data-indentation="1" class="element">&lt;measure <span class="attribute">n</span>="<span class="attributevalue">1</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">analysis.m_sc_22</span>"&gt;</span><br />   <span data-indentation="2" class="element">&lt;staff <span class="attribute">n</span>="<span class="attributevalue">1</span>"&gt;</span><br />     <span data-indentation="3" class="element">&lt;layer <span class="attribute">n</span>="<span class="attributevalue">1</span>"&gt;</span><br />       <span data-indentation="4" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">4</span>" <span class="attribute">oct</span>="<span class="attributevalue">5</span>" <span class="attribute">pname</span>="<span class="attributevalue">c</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">analysis.n_sc_23_3</span>"/&gt;</span><br />       <span data-indentation="4" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">4</span>" <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">b</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">analysis.n_sc_24_3</span>"/&gt;</span><br />       <span data-indentation="4" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">4</span>" <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">a</span>" <span class="attribute">sameas</span>="<span class="attributevalue">analysis.n_sc_25_2</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">analysis.n_sc_25_3</span>"/&gt;</span><br />
                                    <span data-indentation="4" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">4</span>" <span class="attribute">oct</span>="<span class="attributevalue">5</span>" <span class="attribute">pname</span>="<span class="attributevalue">e</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">analysis.n_sc_26_3</span>"/&gt;</span><br />     <span data-indentation="3" class="element">&lt;/layer&gt;</span><br />     <span data-indentation="3" class="element">&lt;layer <span class="attribute">n</span>="<span class="attributevalue">2</span>"&gt;</span><br />
                                    <span data-indentation="4" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">4</span>" <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">a</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">analysis.n_sc_23_2</span>"/&gt;</span><br />       <span data-indentation="4" class="element">&lt;note <span class="attribute">accid</span>="<span class="attributevalue">s</span>" <span class="attribute">dur</span>="<span class="attributevalue">4</span>" <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">g</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">analysis.n_sc_24_2</span>"/&gt;</span><br />       <span data-indentation="4" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">4</span>" <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">a</span>" <span class="attribute">sameas</span>="<span class="attributevalue">analysis.n_sc_25_3</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">analysis.n_sc_25_2</span>"/&gt;</span><br />
                                    <span data-indentation="4" class="element">&lt;beam&gt;</span><br />         <span data-indentation="5" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">8</span>" <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">g</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">analysis.n_sc_26_2</span>"/&gt;</span><br />         <span data-indentation="5" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">8</span>" <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">a</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">analysis.n_sc_27_2</span>"/&gt;</span><br />       <span data-indentation="4" class="element">&lt;/beam&gt;</span><br />     <span data-indentation="3" class="element">&lt;/layer&gt;</span><br />   <span data-indentation="2" class="element">&lt;/staff&gt;</span><br />   <span data-indentation="2" class="element">&lt;staff <span class="attribute">n</span>="<span class="attributevalue">2</span>"&gt;</span><br />
                                  <span data-indentation="3" class="element">&lt;layer <span class="attribute">n</span>="<span class="attributevalue">1</span>"&gt;</span><br />       <span data-indentation="4" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">4</span>" <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">e</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">analysis.n_sc_23_1</span>"/&gt;</span><br />       <span data-indentation="4" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">4</span>" <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">d</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">analysis.n_sc_24_1</span>"/&gt;</span><br />       <span data-indentation="4" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">4</span>" <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">e</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">analysis.n_sc_25_1</span>"/&gt;</span><br />       <span data-indentation="4" class="element">&lt;beam&gt;</span><br />         <span data-indentation="5" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">8</span>" <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">d</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">analysis.n_sc_26_1</span>"/&gt;</span><br />
                                      <span data-indentation="5" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">8</span>" <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">c</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">analysis.n_sc_27_1</span>"/&gt;</span><br />       <span data-indentation="4" class="element">&lt;/beam&gt;</span><br />     <span data-indentation="3" class="element">&lt;/layer&gt;</span><br />
                                  <span data-indentation="3" class="element">&lt;layer <span class="attribute">n</span>="<span class="attributevalue">2</span>"&gt;</span><br />       <span data-indentation="4" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">4</span>" <span class="attribute">oct</span>="<span class="attributevalue">3</span>" <span class="attribute">pname</span>="<span class="attributevalue">a</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">n_sc_23_0</span>"/&gt;</span><br />       <span data-indentation="4" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">4</span>" <span class="attribute">oct</span>="<span class="attributevalue">3</span>" <span class="attribute">pname</span>="<span class="attributevalue">b</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">n_sc_24_0</span>"/&gt;</span><br />       <span data-indentation="4" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">4</span>" <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">c</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">n_sc_25_0</span>"/&gt;</span><br />       <span data-indentation="4" class="element">&lt;beam&gt;</span><br />
                                      <span data-indentation="5" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">8</span>" <span class="attribute">oct</span>="<span class="attributevalue">3</span>" <span class="attribute">pname</span>="<span class="attributevalue">b</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">n_sc_26_0</span>"/&gt;</span><br />         <span data-indentation="5" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">8</span>" <span class="attribute">oct</span>="<span class="attributevalue">3</span>" <span class="attribute">pname</span>="<span class="attributevalue">a</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">n_sc_27_0</span>"/&gt;</span><br />       <span data-indentation="4" class="element">&lt;/beam&gt;</span><br />
                                  <span data-indentation="3" class="element">&lt;/layer&gt;</span><br />   <span data-indentation="2" class="element">&lt;/staff&gt;</span><br />
                              <span data-indentation="1" class="element">&lt;/measure&gt;</span>     
                           </div>
                           <p>While <span class="att">copyof</span> and <span class="att">sameas</span> have defined semantics, the <span class="att">corresp</span> may be used to create user-defined relationships between
                              elements. The example below demonstrates the encoding of a relationship between #note3
                              and the fermata, even though the fermata is not placed directly above the note.
                           </p>
                           <div id="index.xml-egXML-d39e10138" class="pre egXML_valid">
                              <span data-indentation="1" class="element">&lt;measure <span class="attribute">n</span>="<span class="attributevalue">1</span>" <span class="attribute">right</span>="<span class="attributevalue">end</span>"&gt;</span><br />   <span data-indentation="2" class="element">&lt;staff <span class="attribute">n</span>="<span class="attributevalue">1</span>"&gt;</span><br />     <span data-indentation="3" class="element">&lt;layer <span class="attribute">n</span>="<span class="attributevalue">1</span>"&gt;</span><br />       <span data-indentation="4" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">4</span>" <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">c</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">analysis.note1</span>"/&gt;</span><br />       <span data-indentation="4" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">4</span>" <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">d</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">analysis.note2</span>"/&gt;</span><br />       <span data-indentation="4" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">2</span>" <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">e</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">analysis.note3</span>"/&gt;</span><br />     <span data-indentation="3" class="element">&lt;/layer&gt;</span><br />   <span data-indentation="2" class="element">&lt;/staff&gt;</span><br />   <span data-indentation="2" class="element">&lt;fermata <span class="attribute">corresp</span>="<span class="attributevalue">#analysis.note3</span>" <span class="attribute">place</span>="<span class="attributevalue">above</span>" <span class="attribute">tstamp</span>="<span class="attributevalue">4.75</span>"/&gt;</span><br />
                              <span data-indentation="1" class="element">&lt;/measure&gt;</span>     
                           </div>
                           <p>The <span class="att">corresp</span> attribute only marks the correspondence between the current element
                              and one or more other entities. To describe the nature of the correspondence, one
                              must
                              use <a class="link_odd_elementSpec" href="/documentation/2.1.1/annot">annot</a>.
                           </p>
                           <p>The <span class="att">next</span> and
                              <span class="att">prev</span> attributes point to elements which follow or precede the
                              current element in some fashion other than that indicated by encoding order. The use
                              of
                              these attributes helps to avoid confusion in the sequence of events, for example,
                              in
                              voice leading across layers or staves, when the encoding reflects the physical
                              arrangement of voices. In the second measure of the following example, the target
                              of the
                              next attribute occurs after the pointing element in time, but before it in encoding
                              order:
                           </p>
                           <figure class="figure">
                              <figcaption class="caption">Figure 23. Bach Chorale,
                                 <span class="titlem">Ach Gott, vom Himmel sieh' darein</span>, m.
                                 6-7
                              </figcaption><img src="./Images/modules/analysis/chor003_m6-7.png" alt="Bach Chorale, , m. 6-7" class="graphic" style=" height:200px;" ></figure>
                           <div id="index.xml-egXML-d39e10181" class="pre egXML_valid">
                              <span data-indentation="1" class="element">&lt;measure <span class="attribute">n</span>="<span class="attributevalue">6</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">analysis.m_sc_62</span>"&gt;</span><br />   <span data-indentation="2" class="element">&lt;staff <span class="attribute">n</span>="<span class="attributevalue">1</span>"&gt;</span><br />     <span data-indentation="3" class="element">&lt;layer <span class="attribute">n</span>="<span class="attributevalue">1</span>"&gt;</span><br />       <span data-indentation="4" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">4</span>" <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">g</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">analysis.n_sc_63_3</span>"/&gt;</span><br />       <span data-indentation="4" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">4</span>" <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">a</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">analysis.n_sc_65_3</span>"/&gt;</span><br />       <span data-indentation="4" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">4</span>" <span class="attribute">fermata</span>="<span class="attributevalue">above</span>" <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">b</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">analysis.n_sc_67_3</span>"/&gt;</span><br />       <span data-indentation="4" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">4</span>" <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">g</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">analysis.n_sc_68_3</span>"/&gt;</span><br />     <span data-indentation="3" class="element">&lt;/layer&gt;</span><br />     <span data-indentation="3" class="element">&lt;layer <span class="attribute">n</span>="<span class="attributevalue">2</span>"&gt;</span><br />
                                    <span data-indentation="4" class="element">&lt;beam&gt;</span><br />         <span data-indentation="5" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">8</span>" <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">e</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">analysis.n_sc_63_2</span>"/&gt;</span><br />         <span data-indentation="5" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">8</span>" <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">g</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">analysis.n_sc_64_2</span>"/&gt;</span><br />       <span data-indentation="4" class="element">&lt;/beam&gt;</span><br />       <span data-indentation="4" class="element">&lt;beam&gt;</span><br />         <span data-indentation="5" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">8</span>" <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">f</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">analysis.n_sc_65_2</span>"/&gt;</span><br />         <span data-indentation="5" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">8</span>" <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">e</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">analysis.n_sc_66_2</span>"/&gt;</span><br />       <span data-indentation="4" class="element">&lt;/beam&gt;</span><br />       <span data-indentation="4" class="element">&lt;note <span class="attribute">accid</span>="<span class="attributevalue">s</span>" <span class="attribute">dur</span>="<span class="attributevalue">4</span>" <span class="attribute">next</span>="<span class="attributevalue">analysis.n_sc_67_0</span>" <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">d</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">analysis.n_sc_67_2</span>"/&gt;</span><br />       <span data-indentation="4" class="element">&lt;beam&gt;</span><br />         <span data-indentation="5" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">8</span>" <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">e</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">analysis.n_sc_68_1</span>"/&gt;</span><br />         <span data-indentation="5" class="element">&lt;note <span class="attribute">accid</span>="<span class="attributevalue">n</span>" <span class="attribute">dur</span>="<span class="attributevalue">8</span>" <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">d</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">analysis.n_sc_69_1</span>"/&gt;</span><br />       <span data-indentation="4" class="element">&lt;/beam&gt;</span><br />     <span data-indentation="3" class="element">&lt;/layer&gt;</span><br />   <span data-indentation="2" class="element">&lt;/staff&gt;</span><br />   <span data-indentation="2" class="element">&lt;staff <span class="attribute">n</span>="<span class="attributevalue">2</span>"&gt;</span><br />
                                  <span data-indentation="3" class="element">&lt;layer <span class="attribute">n</span>="<span class="attributevalue">1</span>"&gt;</span><br />       <span data-indentation="4" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">4</span>" <span class="attribute">oct</span>="<span class="attributevalue">3</span>" <span class="attribute">pname</span>="<span class="attributevalue">b</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">analysis.n_sc_63_1</span>"/&gt;</span><br />       <span data-indentation="4" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">4</span>" <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">c</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">analysis.n_sc_65_1</span>"/&gt;</span><br />       <span data-indentation="4" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">4</span>" <span class="attribute">oct</span>="<span class="attributevalue">3</span>" <span class="attribute">pname</span>="<span class="attributevalue">f</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">analysis.n_sc_67_1</span>"/&gt;</span><br />       <span data-indentation="4" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">4</span>" <span class="attribute">oct</span>="<span class="attributevalue">3</span>" <span class="attribute">pname</span>="<span class="attributevalue">b</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">analysis.n_sc_68_2</span>"/&gt;</span><br />     <span data-indentation="3" class="element">&lt;/layer&gt;</span><br />     <span data-indentation="3" class="element">&lt;layer <span class="attribute">n</span>="<span class="attributevalue">1</span>"&gt;</span><br />       <span data-indentation="4" class="element">&lt;beam&gt;</span><br />         <span data-indentation="5" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">8</span>" <span class="attribute">oct</span>="<span class="attributevalue">3</span>" <span class="attribute">pname</span>="<span class="attributevalue">e</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">n_sc_63_0</span>"/&gt;</span><br />         <span data-indentation="5" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">8</span>" <span class="attribute">oct</span>="<span class="attributevalue">3</span>" <span class="attribute">pname</span>="<span class="attributevalue">d</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">n_sc_64_0</span>"/&gt;</span><br />       <span data-indentation="4" class="element">&lt;/beam&gt;</span><br />
                                    <span data-indentation="4" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">4</span>" <span class="attribute">oct</span>="<span class="attributevalue">3</span>" <span class="attribute">pname</span>="<span class="attributevalue">c</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">n_sc_65_0</span>"/&gt;</span><br />       <span data-indentation="4" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">4</span>" <span class="attribute">fermata</span>="<span class="attributevalue">below</span>" <span class="attribute">oct</span>="<span class="attributevalue">2</span>" <span class="attribute">pname</span>="<span class="attributevalue">b</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">n_sc_67_0</span>"/&gt;</span><br />       <span data-indentation="4" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">4</span>" <span class="attribute">oct</span>="<span class="attributevalue">3</span>" <span class="attribute">pname</span>="<span class="attributevalue">e</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">n_sc_68_0</span>"/&gt;</span><br />     <span data-indentation="3" class="element">&lt;/layer&gt;</span><br />   <span data-indentation="2" class="element">&lt;/staff&gt;</span><br />
                              <span data-indentation="1" class="element">&lt;/measure&gt;</span><br />
                              <span data-indentation="1" class="element">&lt;measure <span class="attribute">n</span>="<span class="attributevalue">7</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">m_sc_70</span>"&gt;</span><br />   <span data-indentation="2" class="element">&lt;staff <span class="attribute">n</span>="<span class="attributevalue">1</span>"&gt;</span><br />     <span data-indentation="3" class="element">&lt;layer <span class="attribute">n</span>="<span class="attributevalue">1</span>"&gt;</span><br />       <span data-indentation="4" class="element">&lt;beam&gt;</span><br />         <span data-indentation="5" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">8</span>" <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">a</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">analysis.n_sc_71_3</span>"/&gt;</span><br />         <span data-indentation="5" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">8</span>" <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">b</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">analysis.n_sc_72_3</span>"/&gt;</span><br />       <span data-indentation="4" class="element">&lt;/beam&gt;</span><br />       <span data-indentation="4" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">4</span>" <span class="attribute">oct</span>="<span class="attributevalue">5</span>" <span class="attribute">pname</span>="<span class="attributevalue">c</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">analysis.n_sc_73_3</span>"/&gt;</span><br />
                                    <span data-indentation="4" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">4</span>" <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">b</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">analysis.n_sc_75_3</span>"/&gt;</span><br />       <span data-indentation="4" class="element">&lt;beam&gt;</span><br />         <span data-indentation="5" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">8</span>" <span class="attribute">oct</span>="<span class="attributevalue">5</span>" <span class="attribute">pname</span>="<span class="attributevalue">c</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">analysis.n_sc_76_3</span>"/&gt;</span><br />         <span data-indentation="5" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">8</span>" <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">b</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">analysis.n_sc_77_3</span>"/&gt;</span><br />       <span data-indentation="4" class="element">&lt;/beam&gt;</span><br />     <span data-indentation="3" class="element">&lt;/layer&gt;</span><br />     <span data-indentation="3" class="element">&lt;layer <span class="attribute">n</span>="<span class="attributevalue">2</span>"&gt;</span><br />       <span data-indentation="4" class="element">&lt;beam&gt;</span><br />         <span data-indentation="5" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">8</span>" <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">c</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">analysis.n_sc_71_1</span>"/&gt;</span><br />
                                      <span data-indentation="5" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">8</span>" <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">d</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">analysis.n_sc_72_1</span>"/&gt;</span><br />       <span data-indentation="4" class="element">&lt;/beam&gt;</span><br />       <span data-indentation="4" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">4</span>" <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">a</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">analysis.n_sc_73_2</span>"/&gt;</span><br />       <span data-indentation="4" class="element">&lt;note <span class="attribute">accid</span>="<span class="attributevalue">s</span>" <span class="attribute">dur</span>="<span class="attributevalue">4</span>" <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">g</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">analysis.n_sc_75_2</span>"/&gt;</span><br />       <span data-indentation="4" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">4</span>" <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">a</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">analysis.n_sc_76_2</span>"/&gt;</span><br />     <span data-indentation="3" class="element">&lt;/layer&gt;</span><br />     <span data-indentation="3" class="element">&lt;layer <span class="attribute">n</span>="<span class="attributevalue">3</span>"&gt;</span><br />       <span data-indentation="4" class="element">&lt;space <span class="attribute">dur</span>="<span class="attributevalue">4</span>"/&gt;</span><br />       <span data-indentation="4" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">4</span>" <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">e</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">analysis.n_sc_73_1</span>"/&gt;</span><br />       <span data-indentation="4" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">4</span>" <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">e</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">analysis.n_sc_75_1</span>"/&gt;</span><br />       <span data-indentation="4" class="element">&lt;beam&gt;</span><br />         <span data-indentation="5" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">8</span>" <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">e</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">analysis.n_sc_76_1</span>"/&gt;</span><br />
                                      <span data-indentation="5" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">8</span>" <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">d</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">analysis.n_sc_77_1</span>"/&gt;</span><br />       <span data-indentation="4" class="element">&lt;/beam&gt;</span><br />     <span data-indentation="3" class="element">&lt;/layer&gt;</span><br />
                                <span data-indentation="2" class="element">&lt;/staff&gt;</span><br />   <span data-indentation="2" class="element">&lt;staff <span class="attribute">n</span>="<span class="attributevalue">2</span>"&gt;</span><br />
                                  <span data-indentation="3" class="element">&lt;layer <span class="attribute">n</span>="<span class="attributevalue">1</span>"&gt;</span><br />       <span data-indentation="4" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">4</span>" <span class="attribute">next</span>="<span class="attributevalue">analysis.n_sc_73_2</span>" <span class="attribute">oct</span>="<span class="attributevalue">3</span>" <span class="attribute">pname</span>="<span class="attributevalue">a</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">analysis.n_sc_71_2</span>"/&gt;</span><br />     <span data-indentation="3" class="element">&lt;/layer&gt;</span><br />     <span data-indentation="3" class="element">&lt;layer <span class="attribute">n</span>="<span class="attributevalue">2</span>"&gt;</span><br />
                                    <span data-indentation="4" class="element">&lt;note <span class="attribute">accid</span>="<span class="attributevalue">n</span>" <span class="attribute">dur</span>="<span class="attributevalue">4</span>" <span class="attribute">oct</span>="<span class="attributevalue">3</span>" <span class="attribute">pname</span>="<span class="attributevalue">f</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">n_sc_71_0</span>"/&gt;</span><br />       <span data-indentation="4" class="element">&lt;beam&gt;</span><br />         <span data-indentation="5" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">8</span>" <span class="attribute">oct</span>="<span class="attributevalue">3</span>" <span class="attribute">pname</span>="<span class="attributevalue">c</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">n_sc_73_0</span>"/&gt;</span><br />
                                      <span data-indentation="5" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">8</span>" <span class="attribute">oct</span>="<span class="attributevalue">3</span>" <span class="attribute">pname</span>="<span class="attributevalue">d</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">n_sc_74_0</span>"/&gt;</span><br />       <span data-indentation="4" class="element">&lt;/beam&gt;</span><br />       <span data-indentation="4" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">4</span>" <span class="attribute">oct</span>="<span class="attributevalue">3</span>" <span class="attribute">pname</span>="<span class="attributevalue">e</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">n_sc_75_0</span>"/&gt;</span><br />
                                    <span data-indentation="4" class="element">&lt;beam&gt;</span><br />         <span data-indentation="5" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">8</span>" <span class="attribute">oct</span>="<span class="attributevalue">2</span>" <span class="attribute">pname</span>="<span class="attributevalue">a</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">n_sc_76_0</span>"/&gt;</span><br />         <span data-indentation="5" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">8</span>" <span class="attribute">oct</span>="<span class="attributevalue">2</span>" <span class="attribute">pname</span>="<span class="attributevalue">b</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">n_sc_77_0</span>"/&gt;</span><br />       <span data-indentation="4" class="element">&lt;/beam&gt;</span><br />
                                  <span data-indentation="3" class="element">&lt;/layer&gt;</span><br />   <span data-indentation="2" class="element">&lt;/staff&gt;</span><br />
                              <span data-indentation="1" class="element">&lt;/measure&gt;</span>     
                           </div>
                           <p>This attribute may also be
                              useful to clarify a sequence of entites which occurs across some form of interruption,
                              in this case, notes before and after a system or page break where there is no custos
                              or
                              direct in the source:
                           </p>
                           <div id="index.xml-egXML-d39e10346" class="pre egXML_valid">
                              <span data-indentation="1" class="element">&lt;measure <span class="attribute">n</span>="<span class="attributevalue">1</span>"&gt;</span><br />   <span data-indentation="2" class="element">&lt;staff <span class="attribute">n</span>="<span class="attributevalue">1</span>"&gt;</span><br />
                                  <span data-indentation="3" class="element">&lt;layer&gt;</span><br />       <span data-indentation="4" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">4</span>" <span class="attribute">next</span>="<span class="attributevalue">analysis.m1s1e2</span>" <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">f</span>" <span class="attribute">stem.dir</span>="<span class="attributevalue">up</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">analysis.m1s1e1</span>"/&gt;</span><br />       <span data-indentation="4" class="element">&lt;pb/&gt;</span><br />       <span data-indentation="4" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">8</span>" <span class="attribute">next</span>="<span class="attributevalue">m1s1e3</span>" <span class="attribute">oct</span>="<span class="attributevalue">3</span>" <span class="attribute">pname</span>="<span class="attributevalue">b</span>" <span class="attribute">prev</span>="<span class="attributevalue">analysis.m1s1e1</span>" <span class="attribute">stem.dir</span>="<span class="attributevalue">up</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">analysis.m1s1e2</span>"/&gt;</span><br />       <span data-indentation="4" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">8</span>" <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">c</span>" <span class="attribute">prev</span>="<span class="attributevalue">analysis.m1s1e2</span>" <span class="attribute">stem.dir</span>="<span class="attributevalue">up</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">analysis.m1s1e3</span>"/&gt;</span><br />
                                  <span data-indentation="3" class="element">&lt;/layer&gt;</span><br />   <span data-indentation="2" class="element">&lt;/staff&gt;</span><br />
                              <span data-indentation="1" class="element">&lt;/measure&gt;</span>     
                           </div>
                           <p>A one-to-many relationship
                              between the current element and the entities being referred to can be expressed by
                              using
                              a list of space-separated URIs in <span class="att">corresp</span>.
                           </p>
                           <p>The <span class="att">synch</span> attribute points to an element that is synchronous with; that
                              is, begins at the same moment in time, as the current element. It is useful when the
                              encoding order differs from the order in which entities occur in time.
                           </p>
                           <p>The <span class="att">when</span> attribute may be used to indicate the point of occurrence of
                              the feature bearing this attribute along a time line. Its value must be the ID of
                              a
                              <a class="link_odd_elementSpec" href="/documentation/2.1.1/when">when</a> element. For more detailed information regarding
                              the use of <span class="att">when</span>, please see <a class="link_ptr" href="/documentation/2.1.1/linkAlign" title="0"><span class="headingNumber">15 </span>Linking and
                                 Alignment</a>.
                           </p>
                        </div>
                        <div class="div2" id="analysisSpecificAttrs">
                           <h2><span class="headingNumber">7.2 </span><span class="head">Event-Specific Analytical
                                 Information</span></h2>
                           <p>In addition to the common analytical attributes, the
                              analysis module also offers other, more specific attributes on certain musical
                              elements:
                           </p>
                           <ul class="specList">
                              
                              <li><span class="specList-classSpec"><a href="/documentation/2.1.1/att.intervalharmonic">att.intervalharmonic</a></span> Attributes that describe harmonic
                                 intervals.
                                 <table class="specDesc">
                                    
                                    <tr>
                                       
                                       <td class="Attribute"><span class="att">inth</span></td>
                                       
                                       <td>encodes the harmonic interval between this note and other pitches occurring at
                                          the same time.
                                       </td>
                                       
                                    </tr>
                                    
                                 </table>
                              </li>
                              
                              <li><span class="specList-classSpec"><a href="/documentation/2.1.1/att.intervallicdesc">att.intervallicdesc</a></span> Attributes that provide for description of
                                 intervallic content.
                                 <table class="specDesc">
                                    
                                    <tr>
                                       
                                       <td class="Attribute"><span class="att">intm</span></td>
                                       
                                       <td>encodes the melodic interval from the previous pitch. The value may be a
                                          general directional indication (u, d, s), an indication of diatonic interval
                                          direction, quality, and size, or a precise numeric value in half steps.
                                       </td>
                                       
                                    </tr>
                                    
                                 </table>
                              </li>
                              
                              <li><span class="specList-classSpec"><a href="/documentation/2.1.1/att.melodicfunction">att.melodicfunction</a></span> Attributes describing melodic function.
                                 <table class="specDesc">
                                    
                                    <tr>
                                       
                                       <td class="Attribute"><span class="att">mfunc</span></td>
                                       
                                       <td>describes melodic function using Humdrum **embel syntax.</td>
                                       
                                    </tr>
                                    
                                 </table>
                              </li>
                              
                              <li><span class="specList-classSpec"><a href="/documentation/2.1.1/att.harmonicfunction">att.harmonicfunction</a></span> Attributes describing the harmonic function of a
                                 single pitch.
                                 <table class="specDesc">
                                    
                                    <tr>
                                       
                                       <td class="Attribute"><span class="att">deg</span></td>
                                       
                                       <td>captures relative scale degree information using Humdrum **deg syntax -- an
                                          optional indicator of melodic approach (^ = ascending approach, v = descending
                                          approach), a scale degree value (1 = tonic ... 7 = leading tone), and an
                                          optional indication of chromatic alteration. The amount of chromatic alternation
                                          is not indicated.
                                       </td>
                                       
                                    </tr>
                                    
                                 </table>
                              </li>
                              
                              <li><span class="specList-classSpec"><a href="/documentation/2.1.1/att.pitchclass">att.pitchclass</a></span>
                                 Attributes that describe pitch class.
                                 <table class="specDesc">
                                    
                                    <tr>
                                       
                                       <td class="Attribute"><span class="att">pclass</span></td>
                                       
                                       <td>holds pitch class information.</td>
                                       
                                    </tr>
                                    
                                 </table>
                              </li>
                              
                              <li><span class="specList-classSpec"><a href="/documentation/2.1.1/att.solfa">att.solfa</a></span>
                                 Attributes that specify pitch using sol-fa.
                                 <table class="specDesc">
                                    
                                    <tr>
                                       
                                       <td class="Attribute"><span class="att">psolfa</span></td>
                                       
                                       <td>contains sol-fa designation, e.g., do, re, mi, etc., in either a fixed or
                                          movable Do system.
                                       </td>
                                       
                                    </tr>
                                    
                                 </table>
                              </li>
                              
                           </ul>
                           <div class="div3" id="analysisMelodicIntervals">
                              <h3><span class="headingNumber">7.2.1
                                    </span><span class="head">Melodic Intervals</span></h3>
                              <p>The<span class="att">intm</span> attribute offers several methods for encoding the melodic interval from
                                 a preceding pitch. First, Parsons Code allows for description of the contour of the
                                 melody in very general terms; that is, as up, down, or same note. Parsons Code is
                                 helpful for identifying musical works with clearly defined melodies and analyzing
                                 the
                                 relationship between successive notes of monophonic tunes. For more information about
                                 the Parsons Code, please see the "The Directory of Tunes and Musical Themes" by Denys
                                 Parsons (2002). The next example shows interval relationships indicated by the Parsons
                                 Code:
                              </p>
                              <div id="index.xml-egXML-d39e10411" class="pre egXML_valid">
                                 <span data-indentation="1" class="element">&lt;measure <span class="attribute">n</span>="<span class="attributevalue">1</span>"&gt;</span><br />   <span data-indentation="2" class="element">&lt;staff <span class="attribute">n</span>="<span class="attributevalue">1</span>"&gt;</span><br />     <span data-indentation="3" class="element">&lt;layer&gt;</span><br />       <span data-indentation="4" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">4</span>" <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">c</span>"/&gt;</span><br />       <span data-indentation="4" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">4</span>" <span class="attribute">intm</span>="<span class="attributevalue">u</span>" <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">d</span>"/&gt;</span><br />       <span data-indentation="4" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">4</span>" <span class="attribute">intm</span>="<span class="attributevalue">u</span>" <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">e</span>"/&gt;</span><br />
                                       <span data-indentation="4" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">4</span>" <span class="attribute">intm</span>="<span class="attributevalue">u</span>" <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">f</span>"/&gt;</span><br />       <span data-indentation="4" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">2</span>" <span class="attribute">intm</span>="<span class="attributevalue">u</span>" <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">g</span>"/&gt;</span><br />       <span data-indentation="4" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">2</span>" <span class="attribute">intm</span>="<span class="attributevalue">s</span>" <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">g</span>"/&gt;</span><br />
                                       <span data-indentation="4" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">4</span>" <span class="attribute">intm</span>="<span class="attributevalue">d</span>" <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">f</span>"/&gt;</span><br />     <span data-indentation="3" class="element">&lt;/layer&gt;</span><br />   <span data-indentation="2" class="element">&lt;/staff&gt;</span><br />
                                 <span data-indentation="1" class="element">&lt;/measure&gt;</span>       
                              </div>
                              <p>Alternatively, diatonic
                                 interval quality and size may be indicated by a letter signifying the interval quality
                                 (A= augmented, d= diminished, M = major, m = minor, P = perfect) followed by a number
                                 indicating the size of the interval. The interval direction may be encoded using a
                                 leading plus (+) or minus (-) sign:
                              </p>
                              <div id="index.xml-egXML-d39e10439" class="pre egXML_valid">
                                 <span data-indentation="1" class="element">&lt;measure&gt;</span><br />   <span data-indentation="2" class="element">&lt;staff&gt;</span><br />     <span data-indentation="3" class="element">&lt;layer&gt;</span><br />       <span data-indentation="4" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">4</span>" <span class="attribute">oct</span>="<span class="attributevalue">5</span>" <span class="attribute">pname</span>="<span class="attributevalue">c</span>"/&gt;</span><br />       <span data-indentation="4" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">4</span>" <span class="attribute">intm</span>="<span class="attributevalue">+M2</span>" <span class="attribute">oct</span>="<span class="attributevalue">5</span>" <span class="attribute">pname</span>="<span class="attributevalue">d</span>"/&gt;</span><br />       <span data-indentation="4" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">4</span>" <span class="attribute">intm</span>="<span class="attributevalue">-M2</span>" <span class="attribute">oct</span>="<span class="attributevalue">5</span>" <span class="attribute">pname</span>="<span class="attributevalue">c</span>"/&gt;</span><br />
                                       <span data-indentation="4" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">4</span>" <span class="attribute">intm</span>="<span class="attributevalue">-m2</span>" <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">b</span>"/&gt;</span><br />       <span data-indentation="4" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">4</span>" <span class="attribute">intm</span>="<span class="attributevalue">-P8</span>" <span class="attribute">oct</span>="<span class="attributevalue">3</span>" <span class="attribute">pname</span>="<span class="attributevalue">b</span>"/&gt;</span><br />     <span data-indentation="3" class="element">&lt;/layer&gt;</span><br />   <span data-indentation="2" class="element">&lt;/staff&gt;</span><br />
                                 <span data-indentation="1" class="element">&lt;/measure&gt;</span>       
                              </div>
                              <p>As a third option, signed
                                 integers may be used to record the difference in half steps between the previous pitch
                                 and the current one. Decimal values accommodate the description of microtonal
                                 intervals:
                              </p>
                              <div id="index.xml-egXML-d39e10462" class="pre egXML_valid">
                                 <span data-indentation="1" class="element">&lt;measure&gt;</span><br />   <span data-indentation="2" class="element">&lt;staff&gt;</span><br />     <span data-indentation="3" class="element">&lt;layer&gt;</span><br />       <span data-indentation="4" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">4</span>" <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">c</span>"/&gt;</span><br />       <span data-indentation="4" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">4</span>" <span class="attribute">intm</span>="<span class="attributevalue">1.1</span>" <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">d</span>"/&gt;</span><br />       <span data-indentation="4" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">4</span>" <span class="attribute">intm</span>="<span class="attributevalue">7.9</span>" <span class="attribute">oct</span>="<span class="attributevalue">5</span>" <span class="attribute">pname</span>="<span class="attributevalue">d</span>"/&gt;</span><br />
                                       <span data-indentation="4" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">4</span>" <span class="attribute">intm</span>="<span class="attributevalue">-2.334</span>" <span class="attribute">oct</span>="<span class="attributevalue">5</span>" <span class="attribute">pname</span>="<span class="attributevalue">c</span>"/&gt;</span><br />     <span data-indentation="3" class="element">&lt;/layer&gt;</span><br />   <span data-indentation="2" class="element">&lt;/staff&gt;</span><br />
                                 <span data-indentation="1" class="element">&lt;/measure&gt;</span>       
                              </div>
                           </div>
                           <div class="div3" id="analysisMelodicFunction">
                              <h3><span class="headingNumber">7.2.2 </span><span class="head">Melodic Function</span></h3>
                              <p>The <span class="att">mfunc</span>
                                 attribute describes melodic function of a <a class="link_odd_elementSpec" href="/documentation/2.1.1/note">note</a> or
                                 <a class="link_odd_elementSpec" href="/documentation/2.1.1/uneume">uneume</a> using the Humdrum **embel syntax. In the
                                 following example, the note B is labeled as a lower neighbor while all other notes
                                 are
                                 labeled as chord tones:
                              </p>
                              <div id="index.xml-egXML-d39e10495" class="pre egXML_valid">
                                 <span data-indentation="1" class="element">&lt;measure <span class="attribute">n</span>="<span class="attributevalue">2</span>"&gt;</span><br />   <span data-indentation="2" class="element">&lt;staff <span class="attribute">n</span>="<span class="attributevalue">1</span>"&gt;</span><br />     <span data-indentation="3" class="element">&lt;layer&gt;</span><br />       <span data-indentation="4" class="element">&lt;chord <span class="attribute">dur</span>="<span class="attributevalue">4</span>" <span class="attribute">stem.dir</span>="<span class="attributevalue">up</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">analysis.chord1</span>"&gt;</span><br />
                                         <span data-indentation="5" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">4</span>" <span class="attribute">mfunc</span>="<span class="attributevalue">ct</span>" <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">f</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">analysis.m2e1</span>"/&gt;</span><br />         <span data-indentation="5" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">4</span>" <span class="attribute">mfunc</span>="<span class="attributevalue">ct</span>" <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">a</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">analysis.m2e2</span>"/&gt;</span><br />         <span data-indentation="5" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">4</span>" <span class="attribute">mfunc</span>="<span class="attributevalue">ct</span>" <span class="attribute">oct</span>="<span class="attributevalue">5</span>" <span class="attribute">pname</span>="<span class="attributevalue">c</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">analysis.m2e3</span>"/&gt;</span><br />       <span data-indentation="4" class="element">&lt;/chord&gt;</span><br />       <span data-indentation="4" class="element">&lt;note <span class="attribute">accid</span>="<span class="attributevalue">f</span>" <span class="attribute">dur</span>="<span class="attributevalue">4</span>" <span class="attribute">mfunc</span>="<span class="attributevalue">ln</span>" <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">b</span>" <span class="attribute">stem.dir</span>="<span class="attributevalue">down</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">analysis.m2e4</span>"/&gt;</span><br />     <span data-indentation="3" class="element">&lt;/layer&gt;</span><br />
                                   <span data-indentation="2" class="element">&lt;/staff&gt;</span><br />
                                 <span data-indentation="1" class="element">&lt;/measure&gt;</span><br />
                                 <span data-indentation="1" class="element">&lt;measure <span class="attribute">n</span>="<span class="attributevalue">3</span>"&gt;</span><br />   <span data-indentation="2" class="element">&lt;staff <span class="attribute">n</span>="<span class="attributevalue">1</span>"&gt;</span><br />     <span data-indentation="3" class="element">&lt;layer&gt;</span><br />       <span data-indentation="4" class="element">&lt;chord <span class="attribute">dur</span>="<span class="attributevalue">4</span>" <span class="attribute">stem.dir</span>="<span class="attributevalue">up</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">analysis.chord2</span>"&gt;</span><br />
                                         <span data-indentation="5" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">4</span>" <span class="attribute">mfunc</span>="<span class="attributevalue">ct</span>" <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">c</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">analysis.m3e5</span>"/&gt;</span><br />         <span data-indentation="5" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">4</span>" <span class="attribute">mfunc</span>="<span class="attributevalue">ct</span>" <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">e</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">analysis.m3e6</span>"/&gt;</span><br />         <span data-indentation="5" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">4</span>" <span class="attribute">mfunc</span>="<span class="attributevalue">ct</span>" <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">g</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">analysis.m3e7</span>"/&gt;</span><br />       <span data-indentation="4" class="element">&lt;/chord&gt;</span><br />     <span data-indentation="3" class="element">&lt;/layer&gt;</span><br />   <span data-indentation="2" class="element">&lt;/staff&gt;</span><br />
                                 <span data-indentation="1" class="element">&lt;/measure&gt;</span>       
                              </div>
                           </div>
                           <div class="div3" id="analysisHarmonicIntervals">
                              <h3><span class="headingNumber">7.2.3 </span><span class="head">Harmonic Intervals</span></h3>
                              <ul class="specList">
                                 
                                 <li><span class="specList-classSpec"><a href="/documentation/2.1.1/att.intervalharmonic">att.intervalharmonic</a></span> Attributes that describe harmonic
                                    intervals.
                                    <table class="specDesc">
                                       
                                       <tr>
                                          
                                          <td class="Attribute"><span class="att">inth</span></td>
                                          
                                          <td>encodes the harmonic interval between this note and other pitches occurring
                                             at the same time.
                                          </td>
                                          
                                       </tr>
                                       
                                    </table>
                                 </li>
                                 
                              </ul>
                              <p>In contrast with <span class="att">intm</span>, which characterizes melodic
                                 (sequential) intervals, the <span class="att">inth</span> attribute is used to encode
                                 the harmonic interval between the current note and other pitches occurring at the
                                 same
                                 moment in time. The notes of interest may or may not be marked as a <a class="link_odd_elementSpec" href="/documentation/2.1.1/chord">chord</a>. In the markup below, for example, the values of <span class="att">inth</span> capture the harmonic intervals between notes distributed
                                 across multiple staves and layers.
                              </p>
                              <div id="index.xml-egXML-d39e10557" class="pre egXML_valid">
                                 <span data-indentation="1" class="element">&lt;measure&gt;</span><br />   <span data-indentation="2" class="element">&lt;staff&gt;</span><br />     <span data-indentation="3" class="element">&lt;layer <span class="attribute">n</span>="<span class="attributevalue">1</span>"&gt;</span><br />       <span data-indentation="4" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">4</span>" <span class="attribute">inth</span>="<span class="attributevalue">M3 P5</span>" <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">c</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">analysis.e1</span>"/&gt;</span><br />     <span data-indentation="3" class="element">&lt;/layer&gt;</span><br />     <span data-indentation="3" class="element">&lt;layer <span class="attribute">n</span>="<span class="attributevalue">2</span>"&gt;</span><br />       <span data-indentation="4" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">4</span>" <span class="attribute">inth</span>="<span class="attributevalue">M3 m3</span>" <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">e</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">analysis.e2</span>"/&gt;</span><br />     <span data-indentation="3" class="element">&lt;/layer&gt;</span><br />   <span data-indentation="2" class="element">&lt;/staff&gt;</span><br />   <span data-indentation="2" class="element">&lt;staff <span class="attribute">n</span>="<span class="attributevalue">2</span>"&gt;</span><br />     <span data-indentation="3" class="element">&lt;layer <span class="attribute">n</span>="<span class="attributevalue">3</span>"&gt;</span><br />       <span data-indentation="4" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">4</span>" <span class="attribute">inth</span>="<span class="attributevalue">P5 m3</span>" <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">g</span>" <span class="attribute">xml:id</span>="<span class="attributevalue">analysis.e3</span>"/&gt;</span><br />
                                     <span data-indentation="3" class="element">&lt;/layer&gt;</span><br />   <span data-indentation="2" class="element">&lt;/staff&gt;</span><br />
                                 <span data-indentation="1" class="element">&lt;/measure&gt;</span>       
                              </div>
                              <p>Use of the <span class="att">inth</span> permits detailed specification of intervallic information
                                 for every note and its function in relation to other simultaneously-occurring notes
                                 and hence about the harmonic nature of the musical work.
                              </p>
                           </div>
                           <div class="div3" id="analysisScaleDegrees">
                              <h3><span class="headingNumber">7.2.4 </span><span class="head">Scale Degrees</span></h3>
                              <ul class="specList">
                                 
                                 <li><span class="specList-classSpec"><a href="/documentation/2.1.1/att.harmonicfunction">att.harmonicfunction</a></span> Attributes describing the harmonic function of
                                    a single pitch.
                                    <table class="specDesc">
                                       
                                       <tr>
                                          
                                          <td class="Attribute"><span class="att">deg</span></td>
                                          
                                          <td>captures relative scale degree information using Humdrum **deg syntax -- an
                                             optional indicator of melodic approach (^ = ascending approach, v = descending
                                             approach), a scale degree value (1 = tonic ... 7 = leading tone), and an
                                             optional indication of chromatic alteration. The amount of chromatic
                                             alternation is not indicated.
                                          </td>
                                          
                                       </tr>
                                       
                                    </table>
                                 </li>
                                 
                              </ul>
                              <p>The <span class="att">deg</span> attribute can be used to represent
                                 key-dependent scale-degree information for music in major or minor
                                 keys.
                              </p>
                              <p>Scale-degree values are relative to the prevailing major or minor key. In
                                 the case of minor keys, scale degrees are characterized with respect to the harmonic
                                 minor scale. For example, the pitch F in the key of A minor is the submediant (6),
                                 but
                                 F is the lowered submediant (6-) in the key of A major.
                              </p>
                              <p>Melodic approach can be
                                 indicated by a leading caret (^) or lowercase v, representing ascending and descending
                                 approaches, respectively.
                              </p>
                              <p>Chromatic alteration of the scale degree can be
                                 represented using a trailing plus (+) or minus (-) signs, signifying raised or lowered
                                 scale degree, respectively. The actual amount of chromatic alteration is not
                                 indicated.
                              </p>
                              <div id="index.xml-egXML-d39e10607" class="pre egXML_invalid">
                                 <span data-indentation="1" class="element">&lt;note <span class="attribute">deg</span>="<span class="attributevalue">5</span>"/&gt;</span><br />
                                 <span data-indentation="1" class="element">&lt;note <span class="attribute">deg</span>="<span class="attributevalue">5+</span>"/&gt;</span><br />
                                 <span data-indentation="1" class="element">&lt;note <span class="attribute">deg</span>="<span class="attributevalue">^6-</span>"/&gt;</span><br />
                                 <span data-indentation="1" class="element">&lt;note <span class="attribute">deg</span>="<span class="attributevalue">v7</span>"/&gt;</span>       
                              </div>
                           </div>
                           <div class="div3" id="analysisPitchClass">
                              <h3><span class="headingNumber">7.2.5 </span><span class="head">Pitch Class</span></h3>
                              <p>The <span class="att">pclass</span> attribute can be used
                                 to encode information about the pitch class to which a note belongs. The attribute's
                                 value must be an integer less than or equal to 11. It is only allowed on the <a class="link_odd_elementSpec" href="/documentation/2.1.1/note">note</a> element. The <span class="att">pclass</span>
                                 attribute comes from "musical set theory" elaborated first by Howard Hanson and Allen
                                 Forte as a new method for organizing tones. It provides a concept for categorizing
                                 musical objects (notes) and describing their relationships. It is a kind of grouping
                                 and combining, mostly developed in connection with atonal music. However, the concept
                                 of set theory is general and can also be applied to tonal music. A pitch class means
                                 the summary of every pitch with specific characteristics that means a pitch class
                                 set
                                 is an unordered collection of pitches, e.g., every pitch with the name C.
                              </p>
                              <p>A
                                 pitch class may contain a large number of pitches, because different octaves and
                                 enharmonic spellings of pitch make no difference. The notes C, E, and G would be 0,
                                 4
                                 and 7 in pitch class notation, for example, regardless of the octave in which they
                                 are
                                 performed. The example below contains the same pitch in four different enharmonic
                                 spellings, but all are part of the same pitch class. 
                              </p>
                              <div id="index.xml-egXML-d39e10633" class="pre egXML_invalid">
                                 <span data-indentation="1" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">4</span>" <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pclass</span>="<span class="attributevalue">2</span>" <span class="attribute">pname</span>="<span class="attributevalue">d</span>"/&gt;</span><br />
                                 <span data-indentation="1" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">2</span>" <span class="attribute">oct</span>="<span class="attributevalue">5</span>" <span class="attribute">pclass</span>="<span class="attributevalue">2</span>" <span class="attribute">pname</span>="<span class="attributevalue">d</span>"/&gt;</span><br />
                                 <span data-indentation="1" class="element">&lt;note <span class="attribute">accid</span>="<span class="attributevalue">ss</span>" <span class="attribute">dur</span>="<span class="attributevalue">4</span>" <span class="attribute">pclass</span>="<span class="attributevalue">2</span>" <span class="attribute">pname</span>="<span class="attributevalue">c</span>"/&gt;</span><br />
                                 <span data-indentation="1" class="element">&lt;note <span class="attribute">accid</span>="<span class="attributevalue">ff</span>" <span class="attribute">dur</span>="<span class="attributevalue">1</span>" <span class="attribute">pclass</span>="<span class="attributevalue">2</span>" <span class="attribute">pname</span>="<span class="attributevalue">e</span>"/&gt;</span>       
                              </div>
                              <p>For further
                                 information on pitch class set theory, please consult the following sources:
                              </p>
                              <ul>
                                 
                                 <li class="item"><a class="link_ref" href="http://www.mta.ca/faculty/arts-letters/music/pc-set_project/pc-set_new/pages/introduction/toc.html">http://www.mta.ca/faculty/arts-letters/music/pc-set_project/pc-set_new/pages/introduction/toc.html</a></li>
                                 
                                 <li class="item">"Analyzing Atonal Music: Pitch Class Set Theory and its Contexts" by
                                    Michael Schuijler (2008)
                                 </li>
                                 
                                 <li class="item">Cohen, Allen Laurence (2004). Howard Hanson in Theory and
                                    Practice
                                 </li>
                                 
                              </ul>
                           </div>
                           <div class="div3" id="analysisSolmization">
                              <h3><span class="headingNumber">7.2.6 </span><span class="head">Solmization</span></h3>
                              <p>Solmization is a system
                                 which associates a syllable with each note of a musical scale. There are various forms
                                 of solmization used throughout the world. In Europe and North America, solfège is
                                 the
                                 most common practice. In this system, the seven syllables for a major scale are do,
                                 re, mi, fa, so, la and ti. In the ‘fixed-do’ system, the syllable "do" is always
                                 associated with the pitch "c", while in the ‘movable-do’ system, "do" is associated
                                 with the tonic note. The <span class="att">psolfa</span> attribute is only allowed on
                                 <a class="link_odd_elementSpec" href="/documentation/2.1.1/note">note</a> and <a class="link_odd_elementSpec" href="/documentation/2.1.1/uneume">uneume</a>
                                 elements. Its value is unconstrained in order to accommodate various solmization
                                 systems.
                              </p>
                              <div id="index.xml-egXML-d39e10673" class="pre egXML_valid">
                                 <span data-indentation="1" class="element">&lt;measure&gt;</span><br />   <span data-indentation="2" class="element">&lt;staff <span class="attribute">n</span>="<span class="attributevalue">1</span>"&gt;</span><br />
                                     <span data-indentation="3" class="element">&lt;layer&gt;</span><br />       <span data-indentation="4" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">4</span>" <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">c</span>" <span class="attribute">psolfa</span>="<span class="attributevalue">do</span>"/&gt;</span><br />       <span data-indentation="4" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">4</span>" <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">d</span>" <span class="attribute">psolfa</span>="<span class="attributevalue">re</span>"/&gt;</span><br />       <span data-indentation="4" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">4</span>" <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">e</span>" <span class="attribute">psolfa</span>="<span class="attributevalue">mi</span>"/&gt;</span><br />       <span data-indentation="4" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">4</span>" <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">f</span>" <span class="attribute">psolfa</span>="<span class="attributevalue">fa</span>"/&gt;</span><br />     <span data-indentation="3" class="element">&lt;/layer&gt;</span><br />   <span data-indentation="2" class="element">&lt;/staff&gt;</span><br />
                                 <span data-indentation="1" class="element">&lt;/measure&gt;</span>       
                              </div>
                           </div>
                        </div>
                        <div class="div2" id="analysisMetricalConformance">
                           <h2><span class="headingNumber">7.3
                                 </span><span class="head">Metrical Conformance</span></h2>
                           <p>It is often helpful to
                              record whether a given staff, layer, or measure obeys the meter established for it.
                              The
                              following attributes are provided for this purpose:
                           </p>
                           <ul class="specList">
                              
                              <li><span class="specList-classSpec"><a href="/documentation/2.1.1/att.meterconformance">att.meterconformance</a></span> Attributes that provide information about a
                                 structure's conformance to the prevailing meter.
                                 <table class="specDesc">
                                    
                                    <tr>
                                       
                                       <td class="Attribute"><span class="att">metcon</span></td>
                                       
                                       <td>indicates the relationship between the content of a staff or layer and the
                                          prevailing meter.
                                       </td>
                                       
                                    </tr>
                                    
                                 </table>
                              </li>
                              
                              <li><span class="specList-classSpec"><a href="/documentation/2.1.1/att.meterconformance.bar">att.meterconformance.bar</a></span> Attributes that provide information about a
                                 measure's conformance to the prevailing meter.
                                 <table class="specDesc">
                                    
                                    <tr>
                                       
                                       <td class="Attribute"><span class="att">metcon</span></td>
                                       
                                       <td>indicates the relationship between the content of a measure and the prevailing
                                          meter.
                                       </td>
                                       
                                    </tr>
                                    
                                 </table>
                              </li>
                              
                           </ul>
                           <p>When used on <a class="link_odd_elementSpec" href="/documentation/2.1.1/staff">staff</a> or <a class="link_odd_elementSpec" href="/documentation/2.1.1/layer">layer</a> elements, the <span class="att">metcon</span> attribute can be
                              used to indicate if the duration of the contained events is equal to ("c"), less than
                              ("i"), or greater than ("o") that predicted by the time signature. When used on the
                              <a class="link_odd_elementSpec" href="/documentation/2.1.1/measure">measure</a> element, <span class="att">metcon</span> takes
                              a boolean value, where "true" indicates conformance by all staff and layer descendants
                              of the measure.
                           </p>
                           <p>In the first example below, the layer, staff, and measure all
                              match the prevailing meter. In the second example, however, the first layer does not
                              comply with the meter, making the staff containing it and measure as a whole
                              non-compliant. When there is a single layer or when all the layers on a staff agree
                              with
                              each other, metrical compliance can be indicated on the <a class="link_odd_elementSpec" href="/documentation/2.1.1/staff">staff</a> element. When, however, not all layers have the same value for
                              <span class="att">metcon</span>, then it is necessary to omit <span class="att">metcon</span> at the staff level. The value of <span class="att">metcon</span> on the
                              measure level can usually be computed based on the values of its layer and staff
                              sub-elements.
                           </p>
                           <div id="index.xml-egXML-d39e10734" class="pre egXML_valid">
                              <span data-indentation="1" class="element">&lt;measure <span class="attribute">metcon</span>="<span class="attributevalue">true</span>" <span class="attribute">n</span>="<span class="attributevalue">1</span>"&gt;</span><br />   <span data-indentation="2" class="element">&lt;staff <span class="attribute">n</span>="<span class="attributevalue">1</span>"&gt;</span><br />
                                  <span data-indentation="3" class="element">&lt;layer&gt;</span><br />       <span data-indentation="4" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">4</span>" <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">f</span>"/&gt;</span><br />       <span data-indentation="4" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">8</span>" <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">b</span>"/&gt;</span><br />       <span data-indentation="4" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">8</span>" <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">a</span>"/&gt;</span><br />     <span data-indentation="3" class="element">&lt;/layer&gt;</span><br />   <span data-indentation="2" class="element">&lt;/staff&gt;</span><br />
                              <span data-indentation="1" class="element">&lt;/measure&gt;</span>     
                           </div>
                           <div id="index.xml-egXML-d39e10751" class="pre egXML_valid">
                              <span data-indentation="1" class="element">&lt;measure <span class="attribute">metcon</span>="<span class="attributevalue">false</span>" <span class="attribute">n</span>="<span class="attributevalue">1</span>"&gt;</span><br />   <span data-indentation="2" class="element">&lt;staff <span class="attribute">n</span>="<span class="attributevalue">1</span>"&gt;</span><br />
                                  <span data-indentation="3" class="element">&lt;layer <span class="attribute">metcon</span>="<span class="attributevalue">i</span>"&gt;</span><br />       <span data-indentation="4" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">4</span>" <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">f</span>"/&gt;</span><br />       <span data-indentation="4" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">8</span>" <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">b</span>"/&gt;</span><br />     <span data-indentation="3" class="element">&lt;/layer&gt;</span><br />     <span data-indentation="3" class="element">&lt;layer <span class="attribute">metcon</span>="<span class="attributevalue">true</span>"&gt;</span><br />       <span data-indentation="4" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">4</span>" <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">d</span>"/&gt;</span><br />       <span data-indentation="4" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">8</span>" <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">g</span>"/&gt;</span><br />       <span data-indentation="4" class="element">&lt;note <span class="attribute">dur</span>="<span class="attributevalue">8</span>" <span class="attribute">oct</span>="<span class="attributevalue">4</span>" <span class="attribute">pname</span>="<span class="attributevalue">f</span>"/&gt;</span><br />     <span data-indentation="3" class="element">&lt;/layer&gt;</span><br />   <span data-indentation="2" class="element">&lt;/staff&gt;</span><br />
                              <span data-indentation="1" class="element">&lt;/measure&gt;</span>     
                           </div>
                        </div>
                     </section>
                  </div>
               </div>
            </div>
            <div class="panel-grid-cell" style="width: 35%; float: left;">
               <div class="panel widget widget_text panel-first-child panel-last-child">
                  <header class="entry-header">
                     <h1 class="entry-title">
                        MEI Guidelines <small>Version 2.1.1</small></h1>
                  </header>
                  <div class="textwidget">
                     <ul class="guidelinesList">
                        <li><a class="guidelines_mainLink" href="/documentation/2.1.1/chapters">MEI Guidelines</a></li>
                        <li><a class="guidelines_mainLink" href="/documentation/2.1.1/elements">Elements</a></li>
                        <li><a class="guidelines_mainLink" href="/documentation/2.1.1/atts">Attributes</a></li>
                        <li><a class="guidelines_mainLink" href="/documentation/2.1.1/models">Model Classes</a></li>
                        <li><a class="guidelines_mainLink" href="/documentation/2.1.1/data">Data Types</a></li>
                     </ul>
                  </div>
                  <div style="margin: 10px 30px; border-bottom: 0.5px solid #666666; height: 1px;"></div>
                  <h3 class="widget-title">Table of Contents</h3>
                  <div class="textwidget">
                     <ul class="guidelinesList">
                        <li><a href="/documentation/2.1.1/analysis#"><span class="headingNumber">7 </span><span class="head">Analytical
                                 Information</span></a></li>
                        <li><a href="/documentation/2.1.1/analysis#analysisDescribingRelationships"><span class="headingNumber">7.1 </span><span class="head">General Relationships Between
                                 Elements</span></a></li>
                        <li><a href="/documentation/2.1.1/analysis#analysisSpecificAttrs"><span class="headingNumber">7.2 </span><span class="head">Event-Specific Analytical
                                 Information</span></a></li>
                        <li><a href="/documentation/2.1.1/analysis#analysisMelodicIntervals"><span class="headingNumber">7.2.1
                                 </span><span class="head">Melodic Intervals</span></a></li>
                        <li><a href="/documentation/2.1.1/analysis#analysisMelodicFunction"><span class="headingNumber">7.2.2 </span><span class="head">Melodic Function</span></a></li>
                        <li><a href="/documentation/2.1.1/analysis#analysisHarmonicIntervals"><span class="headingNumber">7.2.3 </span><span class="head">Harmonic Intervals</span></a></li>
                        <li><a href="/documentation/2.1.1/analysis#analysisScaleDegrees"><span class="headingNumber">7.2.4 </span><span class="head">Scale Degrees</span></a></li>
                        <li><a href="/documentation/2.1.1/analysis#analysisPitchClass"><span class="headingNumber">7.2.5 </span><span class="head">Pitch Class</span></a></li>
                        <li><a href="/documentation/2.1.1/analysis#analysisSolmization"><span class="headingNumber">7.2.6 </span><span class="head">Solmization</span></a></li>
                        <li><a href="/documentation/2.1.1/analysis#analysisMetricalConformance"><span class="headingNumber">7.3
                                 </span><span class="head">Metrical Conformance</span></a></li>
                     </ul>
                  </div>
               </div>
            </div>
         </div>
      </div>
   </article>
</div>