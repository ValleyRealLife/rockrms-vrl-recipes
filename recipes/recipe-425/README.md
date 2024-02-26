Rock Community / Recipes / [From Matrix to JSON](https://community.rockrms.com/recipes/425/from-matrix-to-json)
<hr>
<p>Input the RawValue of a Matrix-Type Attribute (which is the GUID of an AttributeMatrix), the output will be a JSON-formatted string</p>

<p>Example Lava:</p>
<pre>{[ MatrixToJSON guid:'aaaaaaaaa' ]}</pre>

<p>Example Output:</p>
<pre>{ "AttributeMatrixId": 1234, "Rows": [ { "AttributeMatrixItemId": 1001, "Attribute_Key_A": "Attribute_Value_A1", "Attribute_Key_B": "Attribute_Value_B1", "Attribute_Key_C": "Attribute_Value_C1", "Attribute_Key_D": "Attribute_Value_D1" }, { "AttributeMatrixItemId": 1002, "Attribute_Key_A": "Attribute_Value_A2", "Attribute_Key_B": "Attribute_Value_B2", "Attribute_Key_C": "Attribute_Value_C2", "Attribute_Key_D": "Attribute_Value_D2"}, { "AttributeMatrixItemId": 1003, "Attribute_Key_A": "Attribute_Value_A3", "Attribute_Key_B": "Attribute_Value_B3", "Attribute_Key_C": "Attribute_Value_C3", "Attribute_Key_D": "Attribute_Value_D3"} ] }</pre>

<p>Example Usage:</p>
<pre>
{% capture var_JSON %}
{[ MatrixToJSON guid:'aaaaaaaaa' ]}
{% endcapture %}

{% assign var_Object = var_JSON | FromJSON %}

//- Here is where you can take over with all the Lava tricks in your bag
//- For example:
{{ var_Object.Rows | Size }}
{{ var_Object.Rows[0].AttributeMatrixItemId }}
</pre>

<p>Shout-out to <a href="https://jsonformatter.curiousconcept.com/#" target="_blank">this JSON Formatter &amp; Validator</a>, who has been my faithful friend since Day 1.</p>