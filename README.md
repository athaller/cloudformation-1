A template is a JSON-formatted text file that describes your AWS infrastructure. Templates include several major sections. The Resources section is the only section that is required. The first character in the template must be an open brace ({), and the last character must be a closed brace (}). The following template fragment shows the template structure and sections.

     {
      "AWSTemplateFormatVersion" : "version date",

      "Description" : "JSON string",

      "Metadata" : {
        template metadata
      },

      "Parameters" : {
        set of parameters
      },

      "Mappings" : {
        set of mappings
      },

      "Conditions" : {
        set of conditions
      },

      "Resources" : {
        set of resources
      },

      "Outputs" : {
        set of outputs
      }
    }
Some sections in a template can be in any order. However, as you build your template, it might be helpful to use the logical ordering of the previous example, as values in one section might refer to values from a previous section. The following list gives a brief overview of each section.

**Format Version (optional)**
Specifies the AWS CloudFormation template version that the template conforms to. The template format version is not the same as the API or WSDL version. The template format version can change independently of the API and WSDL versions.

**Description (optional)**
A text string that describes the template. This section must always follow the template format version section.

**Metadata (optional)**
JSON objects that provide additional information about the template.

**Parameters (optional)**
Specifies values that you can pass in to your template at runtime (when you create or update a stack). You can refer to parameters in the Resources and Outputs sections of the template.

**Mappings (optional)**
A mapping of keys and associated values that you can use to specify conditional parameter values, similar to a lookup table. You can match a key to a corresponding value by using the Fn::FindInMap intrinsic function in the Resources and Outputs section.

**Conditions (optional)**
Defines conditions that control whether certain resources are created or whether certain resource properties are assigned a value during stack creation or update. For example, you could conditionally create a resource that depends on whether the stack is for a production or test environment.

**Resources (required)**
Specifies the stack resources and their properties, such as an Amazon Elastic Compute Cloud instance or an Amazon Simple Storage Service bucket. You can refer to resources in the Resources and Outputs sections of the template.

**Outputs (optional)**
Describes the values that are returned whenever you view your stack's properties. For example, you can declare an output for an Amazon S3 bucket name and then call the aws cloudformation describe-stacks AWS CLI command to view the name.
