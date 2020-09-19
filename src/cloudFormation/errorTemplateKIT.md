AWS::Region
Fn::Sub: 'arn:aws:kinesis:${AWS::Region}:${AWS::AccountId}:stream/${Kds}'

                Resource:
                  - Fn::Sub: 'arn:aws:ssm:${AWS::Region}:${AWS::AccountId}:parameter/*'
                  - Fn::Sub: 'arn:aws:dynamodb:${AWS::Region}:${AWS::AccountId}:table/${DDBTable}'
                  - Fn::Sub: 'arn:aws:kinesis:${AWS::Region}:${AWS::AccountId}:stream/${Kds}'
                  - Fn::Sub: 'arn:aws:kinesisvideo:${AWS::Region}:${AWS::AccountId}:stream/*'
                  - Fn::Sub: 'arn:aws:sagemaker:${AWS::Region}:${AWS::AccountId}:endpoint/*'
                  
  *    Please refer to https://docs.aws.amazon.com/sagemaker/latest/dg/algos.html for the ContentType used by SageMaker build-in algorithms.
   * Default: 'image/jpeg'
  DockerImageRepository:
    Type: String
    Default: 528560246458.dkr.ecr.us-east-1.amazonaws.com/kinesisvideosagemakerintegration_release:V1.0.3
    Description: Docker image for Kinesis Video Stream & SageMaker Integration Driver.
  LambdaFunctionBucket:
    Type: String
   * Default: 'kvsit-us-east-1'
  
  *  Default: 'lambda.zip'
