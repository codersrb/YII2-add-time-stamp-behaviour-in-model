# YII2 add time stamp behaviour in model

> Introduce these two below classes in the model
```
use yii\behaviors\TimestampBehavior;
use yii\db\Expression;
```
> Copy below method and changes create and update attribute as per the requirement.
```
    /**
     * @inheritdoc
     */
    public function behaviors()
    {
        return [
            [
                'class' => TimestampBehavior::className(),
                'createdAtAttribute' => 'userAdded',
                'updatedAtAttribute' => 'userModified',
                'value' => new Expression('NOW()'),
            ],
        ];
    }
```
