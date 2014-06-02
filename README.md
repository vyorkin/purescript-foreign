# Module Documentation

## Module Data.Foreign

### Types

    data Foreign :: *

    data ForeignParser a where


### Type Classes

    class ReadForeign a where
      read :: ForeignParser a


### Type Class Instances

    instance applicativeForeignParser :: Prelude.Applicative ForeignParser

    instance applyForeignParser :: Prelude.Apply ForeignParser

    instance bindForeignParser :: Prelude.Bind ForeignParser

    instance functorForeignParser :: Prelude.Functor ForeignParser

    instance monadForeignParser :: Prelude.Monad ForeignParser

    instance readArray :: (ReadForeign a) => ReadForeign [a]

    instance readBoolean :: ReadForeign Prim.Boolean

    instance readError :: ReadForeign Error

    instance readMaybe :: (ReadForeign a) => ReadForeign (Maybe a)

    instance readNumber :: ReadForeign Prim.Number

    instance readString :: ReadForeign Prim.String

    instance showForeign :: Prelude.Show Foreign


### Values

    parseForeign :: forall a. ForeignParser a -> Foreign -> Either Prim.String a

    parseJSON :: forall a. (ReadForeign a) => Prim.String -> Either Prim.String a

    prop :: forall a. (ReadForeign a) => Prim.String -> ForeignParser a