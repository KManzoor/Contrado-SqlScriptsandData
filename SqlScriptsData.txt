USE [QTDev]
GO
/****** Object:  UserDefinedTableType [dbo].[tvp_ProductAttribute]    Script Date: 7/29/2021 11:56:34 AM ******/
CREATE TYPE [dbo].[tvp_ProductAttribute] AS TABLE(
	[ProductID] [int] NOT NULL,
	[AttributeID] [int] NOT NULL,
	[AttributeValue] [varchar](50) NULL
)
GO
/****** Object:  Table [dbo].[Product]    Script Date: 7/29/2021 11:56:34 AM ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[Product](
	[ProductId] [bigint] IDENTITY(1,1) NOT NULL,
	[ProdCatId] [int] NOT NULL,
	[ProdName] [varchar](250) NOT NULL,
	[ProdDescription] [varchar](max) NULL,
 CONSTRAINT [PK_Product] PRIMARY KEY CLUSTERED 
(
	[ProductId] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON, OPTIMIZE_FOR_SEQUENTIAL_KEY = OFF) ON [PRIMARY]
) ON [PRIMARY] TEXTIMAGE_ON [PRIMARY]
GO
/****** Object:  Table [dbo].[ProductAttribute]    Script Date: 7/29/2021 11:56:34 AM ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[ProductAttribute](
	[ProductId] [bigint] NOT NULL,
	[AttributeId] [int] NOT NULL,
	[AttributeValue] [varchar](250) NULL
) ON [PRIMARY]
GO
/****** Object:  Table [dbo].[ProductAttributeLookup]    Script Date: 7/29/2021 11:56:34 AM ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[ProductAttributeLookup](
	[AttributeId] [int] IDENTITY(1,1) NOT NULL,
	[ProdCatId] [int] NOT NULL,
	[AttributeName] [varchar](250) NOT NULL,
 CONSTRAINT [PK_ProductAttributeLookup] PRIMARY KEY CLUSTERED 
(
	[AttributeId] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON, OPTIMIZE_FOR_SEQUENTIAL_KEY = OFF) ON [PRIMARY]
) ON [PRIMARY]
GO
/****** Object:  Table [dbo].[ProductCategory]    Script Date: 7/29/2021 11:56:34 AM ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[ProductCategory](
	[ProdCatId] [int] IDENTITY(1,1) NOT NULL,
	[CategoryName] [varchar](250) NULL,
 CONSTRAINT [PK_ProductCategory] PRIMARY KEY CLUSTERED 
(
	[ProdCatId] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON, OPTIMIZE_FOR_SEQUENTIAL_KEY = OFF) ON [PRIMARY]
) ON [PRIMARY]
GO
SET IDENTITY_INSERT [dbo].[Product] ON 
GO
INSERT [dbo].[Product] ([ProductId], [ProdCatId], [ProdName], [ProdDescription]) VALUES (1, 1, N'BMW', N'BMW')
GO
INSERT [dbo].[Product] ([ProductId], [ProdCatId], [ProdName], [ProdDescription]) VALUES (2, 1, N'MERCEDES', N'MERCEDES')
GO
INSERT [dbo].[Product] ([ProductId], [ProdCatId], [ProdName], [ProdDescription]) VALUES (3, 1, N'KIA', N'KIA')
GO
INSERT [dbo].[Product] ([ProductId], [ProdCatId], [ProdName], [ProdDescription]) VALUES (4, 1, N'HYUNDAI', N'HYUNDAI')
GO
INSERT [dbo].[Product] ([ProductId], [ProdCatId], [ProdName], [ProdDescription]) VALUES (7, 2, N'REALME', N'REALME')
GO
INSERT [dbo].[Product] ([ProductId], [ProdCatId], [ProdName], [ProdDescription]) VALUES (8, 2, N'IPHONE', N'IPHONE')
GO
INSERT [dbo].[Product] ([ProductId], [ProdCatId], [ProdName], [ProdDescription]) VALUES (9, 2, N'POCO', N'POCO')
GO
INSERT [dbo].[Product] ([ProductId], [ProdCatId], [ProdName], [ProdDescription]) VALUES (10, 2, N'REDMI', N'REDMI')
GO
INSERT [dbo].[Product] ([ProductId], [ProdCatId], [ProdName], [ProdDescription]) VALUES (11, 2, N'ONEPLUS', N'ONEPLUS')
GO
INSERT [dbo].[Product] ([ProductId], [ProdCatId], [ProdName], [ProdDescription]) VALUES (12, 2, N'SAMSUNG', N'SAMSUNG')
GO
INSERT [dbo].[Product] ([ProductId], [ProdCatId], [ProdName], [ProdDescription]) VALUES (13, 1, N'TESLA', N'TESLA')
GO
INSERT [dbo].[Product] ([ProductId], [ProdCatId], [ProdName], [ProdDescription]) VALUES (14, 2, N'BALWAS', N'BALWAS')
GO
INSERT [dbo].[Product] ([ProductId], [ProdCatId], [ProdName], [ProdDescription]) VALUES (15, 2, N'SK PATEL', N'SK PATEL')
GO
SET IDENTITY_INSERT [dbo].[Product] OFF
GO
INSERT [dbo].[ProductAttribute] ([ProductId], [AttributeId], [AttributeValue]) VALUES (1, 1, N'BLUE')
GO
INSERT [dbo].[ProductAttribute] ([ProductId], [AttributeId], [AttributeValue]) VALUES (1, 2, N'2020')
GO
INSERT [dbo].[ProductAttribute] ([ProductId], [AttributeId], [AttributeValue]) VALUES (1, 3, N'BMW')
GO
INSERT [dbo].[ProductAttribute] ([ProductId], [AttributeId], [AttributeValue]) VALUES (2, 1, N'Red')
GO
INSERT [dbo].[ProductAttribute] ([ProductId], [AttributeId], [AttributeValue]) VALUES (2, 2, N'2019')
GO
INSERT [dbo].[ProductAttribute] ([ProductId], [AttributeId], [AttributeValue]) VALUES (2, 3, N'Mer')
GO
SET IDENTITY_INSERT [dbo].[ProductAttributeLookup] ON 
GO
INSERT [dbo].[ProductAttributeLookup] ([AttributeId], [ProdCatId], [AttributeName]) VALUES (1, 1, N'Color')
GO
INSERT [dbo].[ProductAttributeLookup] ([AttributeId], [ProdCatId], [AttributeName]) VALUES (2, 1, N'Make')
GO
INSERT [dbo].[ProductAttributeLookup] ([AttributeId], [ProdCatId], [AttributeName]) VALUES (3, 1, N'Model')
GO
INSERT [dbo].[ProductAttributeLookup] ([AttributeId], [ProdCatId], [AttributeName]) VALUES (4, 2, N'RAM')
GO
INSERT [dbo].[ProductAttributeLookup] ([AttributeId], [ProdCatId], [AttributeName]) VALUES (5, 2, N'Front Camera')
GO
INSERT [dbo].[ProductAttributeLookup] ([AttributeId], [ProdCatId], [AttributeName]) VALUES (6, 2, N'Rear Camera')
GO
SET IDENTITY_INSERT [dbo].[ProductAttributeLookup] OFF
GO
SET IDENTITY_INSERT [dbo].[ProductCategory] ON 
GO
INSERT [dbo].[ProductCategory] ([ProdCatId], [CategoryName]) VALUES (1, N'Car')
GO
INSERT [dbo].[ProductCategory] ([ProdCatId], [CategoryName]) VALUES (2, N'Mobile')
GO
SET IDENTITY_INSERT [dbo].[ProductCategory] OFF
GO
ALTER TABLE [dbo].[Product]  WITH CHECK ADD  CONSTRAINT [FK_Product_ProductCategory] FOREIGN KEY([ProdCatId])
REFERENCES [dbo].[ProductCategory] ([ProdCatId])
GO
ALTER TABLE [dbo].[Product] CHECK CONSTRAINT [FK_Product_ProductCategory]
GO
ALTER TABLE [dbo].[ProductAttribute]  WITH CHECK ADD  CONSTRAINT [FK_ProductAttribute_Product] FOREIGN KEY([ProductId])
REFERENCES [dbo].[Product] ([ProductId])
GO
ALTER TABLE [dbo].[ProductAttribute] CHECK CONSTRAINT [FK_ProductAttribute_Product]
GO
ALTER TABLE [dbo].[ProductAttribute]  WITH CHECK ADD  CONSTRAINT [FK_ProductAttribute_ProductAttributeLookup] FOREIGN KEY([AttributeId])
REFERENCES [dbo].[ProductAttributeLookup] ([AttributeId])
GO
ALTER TABLE [dbo].[ProductAttribute] CHECK CONSTRAINT [FK_ProductAttribute_ProductAttributeLookup]
GO
ALTER TABLE [dbo].[ProductAttributeLookup]  WITH CHECK ADD  CONSTRAINT [FK_ProductAttributeLookup_ProductCategory] FOREIGN KEY([ProdCatId])
REFERENCES [dbo].[ProductCategory] ([ProdCatId])
GO
ALTER TABLE [dbo].[ProductAttributeLookup] CHECK CONSTRAINT [FK_ProductAttributeLookup_ProductCategory]
GO
/****** Object:  StoredProcedure [dbo].[usp_DeleteProductWithAttributes]    Script Date: 7/29/2021 11:56:37 AM ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO

CREATE PROCEDURE [dbo].[usp_DeleteProductWithAttributes]

@ProductID INT

AS
BEGIN
DELETE FROM ProductAttribute WHERE ProductId=@ProductID
DELETE FROM Product WHERE ProductId=@ProductID


END

GO
/****** Object:  StoredProcedure [dbo].[usp_GetProductByID]    Script Date: 7/29/2021 11:56:37 AM ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE PROCEDURE [dbo].[usp_GetProductByID]
@ProductID INT =NULL
AS
BEGIN
SELECT p.ProductID,CategoryID=p.ProdCatId,PCategoryName=pc.CategoryName,PName=p.ProdName,PDesc=p.ProdDescription FROM Product p
INNER JOIN ProductCategory pc ON p.ProdCatId=pc.ProdCatId
WHERE (@ProductID IS NULL OR p.ProductId=@ProductID)
END

GO
/****** Object:  StoredProcedure [dbo].[usp_GetProductCategoryAttributeofProduct]    Script Date: 7/29/2021 11:56:37 AM ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE PROCEDURE [dbo].[usp_GetProductCategoryAttributeofProduct] 
	@CategoryID  INT,
	@ProductID   INT
	AS
	BEGIN
		SELECT pal.AttributeId,AttributeName,AttributeValue FROM ProductAttributeLookup pal
		LEFT JOIN ProductAttribute pa ON pal.AttributeId=pa.AttributeId AND pa.ProductId=@ProductID 
		WHERE ProdCatId=@CategoryID --AND (pa.ProductId=NULL OR pa.ProductId=@ProductID )
	END
GO
/****** Object:  StoredProcedure [dbo].[usp_InsertUpdateProduct]    Script Date: 7/29/2021 11:56:37 AM ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO

CREATE PROCEDURE [dbo].[usp_InsertUpdateProduct]
@ProductID INT =NULL OUTPUT,
@CategoryID INT,
@PName VARCHAR(250),
@PDesc VARCHAR(MAX)
AS
BEGIN
	IF(COALESCE(@ProductID,0)=0)
	BEGIN
		INSERT INTO Product(ProdCatId,ProdName,ProdDescription)
		SELECT @CategoryID,@PName,@PDesc
		SET @ProductID=SCOPE_IDENTITY()
	END
	ELSE
	BEGIN
		UPDATE Product SET ProdName=@PName,ProdDescription=@PDesc WHERE ProductId=@ProductID
	END
END

GO
/****** Object:  StoredProcedure [dbo].[usp_InsertUpdateProductAttributes]    Script Date: 7/29/2021 11:56:37 AM ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO

CREATE PROCEDURE [dbo].[usp_InsertUpdateProductAttributes]

@productAttributes dbo.tvp_ProductAttribute  READONLY

AS
BEGIN
INSERT INTO ProductAttribute (ProductId,AttributeId,AttributeValue)
SELECT ProductID,AttributeID,AttributeValue 
FROM @productAttributes tvpPA
WHERE NOT EXISTS(SELECT 1 FROM ProductAttribute PA WHERE PA.ProductID=tvpPA.ProductId AND PA.AttributeID=tvpPA.AttributeId)

UPDATE PA SET PA.AttributeValue=tvpPA.AttributeValue FROM ProductAttribute PA 
INNER JOIN @productAttributes tvpPA ON PA.AttributeId=tvpPA.AttributeID AND PA.ProductId=tvpPA.ProductID



END

GO
