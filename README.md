# hibernate_one2one_uni_fk_composite
一对一单向外键组件（外键是多个字段作为联合主键）
Husband（
  在类中将外键类的对象属性加上此格式的注解：
    @OneToOne
      @JoinColumns(
    	  	{
    			  @JoinColumn(name="wifeId",referencedColumnName="id"),
    			  @JoinColumn(name="wifeName",referencedColumnName="name")
    	  	}
     )
）

Wife（id，name两个属性作为联合主键）（将类注解为@IdClass，并将类中属于主键的属性都注解上@Id）

WifePK（联合主键类——必须实现Serializable接口，必须重写toString和hashCode方法）
