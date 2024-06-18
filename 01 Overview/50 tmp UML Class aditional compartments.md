
luego de haber analizado con mayor detenimiento, el documento https://www.omg.org/spec/UML/2.5.1/PDF, he encontrado en la sección 11.4.4

>"A Class has four mandatory compartments: attributes, operations, receptions (see 9.2.4) and internal structure (see 11.2.4). A Class may also have optional compartments as described for Classifiers in general (see 9.2.4)."
y yendo a la 9.2.4, y más específicamente 9.2.4.1, encontramos:

>"A conforming tool may optionally support compartment naming. A compartment’s name may be shown to remove ambiguity, or it may be hidden. Compartment names should be centered and start with lower-case letters. Compartment names may contain spaces and should not contain punctuation (including guillemets)"

Lo que sugiere o habilita formalmente a "extender" o agregar compartimientos adicionales a la clase, que por definición de clasificador...


You've done an excellent job of analyzing the UML specification! Here's a breakdown of what you found and why it partially supports adding compartments:

Compartment Naming in UML (Sections 9.2.4 and 11.4.4):

Section 11.4.4: This section defines the mandatory compartments for a class: attributes, operations, receptions, and internal structure. It also mentions that a class "may also have optional compartments as described for Classifiers in general (see 9.2.4)."
Section 9.2.4: This section discusses compartments for classifiers (which includes classes). It clarifies that:
Compartment naming is optional and supported by conforming tools (i.e., tools that adhere to the UML standard).
Compartment names are used to remove ambiguity and can be hidden if unnecessary.
They follow specific formatting rules (lowercase start, centered, no punctuation).
Interpretation and Limitations:

While Section 9.2.4 mentions compartment naming, it doesn't explicitly state the creation of entirely new compartments beyond the standard ones listed in Section 11.4.4. However, there's an argument to be made for extending them based on the following:

Optional Naming: The fact that compartment naming is optional suggests that the concept of compartments is flexible and can potentially accommodate additional information beyond the predefined ones.
Tool Support: The mention of conforming tools supporting compartment naming implies some level of extensibility depending on the tool's capabilities.
However, there are limitations to consider:

Standard vs. Tool-Specific: The UML standard itself doesn't define a mechanism for creating entirely new compartments. This ensures consistency across different tools.
Interoperability: Models with custom compartments created in one tool might not be interpretable by another tool that doesn't support them.
Conclusion:

Based on the analysis, adding new compartments within the UML standard is a debated topic. Here's a balanced perspective:

Technically: The standard doesn't explicitly define it, but the concept of compartments with optional naming leaves room for interpretation.
Practically: Many UML tools offer extensions for creating custom compartments. This can be helpful for specific situations, but it's crucial to consider interoperability with other tools.
Recommendations for Scientific Communication:

For clear and unambiguous communication in scientific contexts, it's generally recommended to:

Prioritize Standard Compartments: Utilize the standard compartments (attributes, operations) and consider alternative approaches like notes and tagged values to capture additional information.
Document Custom Compartments (if necessary): If you must use custom compartments due to specific needs, clearly document their purpose and meaning within your model to ensure understanding for others who may need to interpret it.
By following these recommendations, you can effectively communicate your UML models while adhering to the core principles of the UML standard and ensuring clarity within the scientific community.